# Entry 2

##### 02/07/2026

### Content: Progress Made Over The Breaks & Admin Setup

Over winter break and Regents week, I worked on setting up the admin and authentication flow for my project. This was important because the platform needs an owner account before anything else can be managed.

I added code that allows the admin setup page to actually create the first admin account, which is needed before the rest of the platform can be managed. To control access to this page and other routes, I used [Next.js](https://nextjs.org/) middleware, which runs on every request.

In the middleware, I check whether the user is logged in, what role they have, and whether an admin account already exists. If no admin exists yet, users are redirected to the admin setup page. If an admin does exist, that page becomes inaccessible and users are sent to the normal login page instead.

Here is part of the middleware logic:

```ts
const isAuthRoute = AUTH_ROUTES.includes(currentPath);
const isAdminRoute = currentPath.startsWith("/admin");

if (isProtectedRoute || isAuthRoute) {
  const session = await getSession(request);

  if (session) {
    if (isAdminRoute && session.user?.role !== "admin") {
      return NextResponse.redirect(new URL("/", request.url));
    }
    if (AUTH_ROUTES.includes(currentPath)) {
      return NextResponse.redirect(new URL("/", request.url));
    }
  } else {
    const adminExists = await hasAdminUser();
    if (!adminExists && currentPath !== "/auth/admin-setup") {
      return NextResponse.redirect(new URL("/auth/admin-setup", request.url));
    }
    if (adminExists && currentPath === "/auth/admin-setup") {
      return NextResponse.redirect(new URL("/auth/login", request.url));
    }
    if (!isAuthRoute) {
      return NextResponse.redirect(new URL("/auth/login", request.url));
    }
  }
}
```

If a user's role is not admin, they can't access the `/admin` route and are redirected back to the home page. This makes sure that only administrators can access admin related pages.

To keep routing logic organized, I created a routes.ts file to store protected and auth routes:

```js
export const PROTECTED_ROUTES = ["/admin"];
export const AUTH_ROUTES = [
  "/auth/login",
  "/auth/signup",
  "/auth/admin-setup",
  "/auth/forgot-password",
  "/auth/reset-password",
];
```

With these codes, I can check user's authentication state and ensure users get send to the right page on every request.

I also redesigned some of the authentication pages, including the login page, to make them look cleaner and more modern.

![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1770498015/Screenshot_From_2026-02-07_15-55-00_w9bwxu.png)

Now that the admin setup flow actually works and authentication is done, my next step is to start building out the admin dashboard itself.

### Engineering Design Process

I am currently still on Step 5 of the Engineering Design Process, which is prototyping. So far, I have built several initial pages and implemented admin account creation flow. My next goal is to finally built out the amin dashboard page. This is where customizable chatbots and user management happens.

### Skills

##### 1. Logical Reasoning

Logical reasoning was important when writing the middleware. I had to think through different cases, like whether a user is logged in, whether an admin account already exists, and where the user should be redirected. If the logic was wrong, users could get stuck on the wrong page or locked out, so I had to be careful with the conditions.

##### 2. Consideration

Consideration was important when setting up the admin registration flow. The admin setup page should only work once, and after an admin account exists, it shouldn't be accessible anymore. I had to think about how the app should behave during first time setup versus normal use.

### Next Step

My next step is to start building the admin dashboard. This is where admins will manage users, configure settings, and most importantly, customize and publish AI chatbots. I plan to first set up the basic layout and sidebar, then gradually add other features.

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
