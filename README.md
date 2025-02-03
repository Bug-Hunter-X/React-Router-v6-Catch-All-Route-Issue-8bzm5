# React Router v6 Catch-All Route Bug

This repository demonstrates a subtle bug in React Router v6 related to the catch-all route (`/*`).  When a catch-all route is placed below other routes, those subsequent routes are never matched, even if they should be according to the URL.

## Bug Description

The issue arises when combining specific routes with a catch-all route using `Routes`. The catch-all route (`/*`) appears to prevent any following route from being matched. This is unexpected, as we expect that the catch-all route should only match URLs that do not match any of the preceding routes. 

## Reproduction

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that navigating to `/about` displays `404 Not Found` instead of `About`.

## Solution

The solution involves re-ordering the routes.  The catch-all route needs to be placed at the top of the route declarations within the `Routes` component.