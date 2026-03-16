# Entry 4

##### 03/14/2026

### Content: Begin Working On Admin Dashboard

Over the past month, I started working on the admin dashboard pages of my project. The admin dashboard allows admins to manage users, create chatbots, and add knowledge bases. To get ideas for the UI design, I looked on [Dribbble](https://dribbble.com/search/dashboards-black-and-white) by searching for “dashboards black and white” and found a lot of designs that inspired me. I mixed some of the ideas I liked into my own layout. For the sidebar, I made it black with white text. So far, I've built the Overview, Users, Models, and Knowledge Base pages. I used [TailwindCSS](https://tailwindcss.com/) for the layout and [Lucide-react](https://lucide.dev/) for the icons. Right now, I'm using a placeholder logo I found online, but I plan to make my own later.

![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1773628957/imasdasage_hagknw.png)

After finishing the frontend layout, the next step was to secure the `/admin` route using middleware so that only admin users can access the dashboard.

```typescript
if (session) {
  if (isAdminRoute && session.user?.role !== "admin") {
    return NextResponse.redirect(new URL("/", request.url));
  }
  if (AUTH_ROUTES.includes(currentPath)) {
    return NextResponse.redirect(new URL("/", request.url));
  }
} else {
  const adminExists = await hasAdminUser(request);
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
```

Inside my `middleware.ts` file, I added logic to check whether the current route starts with `/admin`. If the user is not an admin, they will be redirected to the home page. This prevents unauthorized users from accessing admin only routes.

Next, I created data access layer functions to retrieve data from the database. For example:

`features/core/user/services/user.service.ts`

```typescript
export const getUserCount = async () => {
  try {
    const result = await db
      .selectFrom("user")
      .select((eb) => eb.fn.count("id").as("count"))
      .executeTakeFirst();
    return Number(result?.count ?? 0);
  } catch (error) {
    console.error("Failed to fetch user count:", error);
    return 0;
  }
};
```

This function, `getUserCount()`, uses Kysely, which is a type safe SQL query builder, to fetch user data from the database. It counts the number of user in the database and returns the total number of users stored in the database. I also created several other similar functions for fetching chatbot models count and total messages count. Then I created a function called `getAdminStats()` that calls these data access layer functions and combines their results. These data are displayed on the overview page of the admin dashboard.

### Engineering Design Process

I am currently between Step 5 **(Create a Prototype)** and Step 6 **(Test and Evaluate the Prototype)** of the Engineering Design Process. So far, I have designed and built the frontend layout of admin dashboards. I also implemented some backend data access functions for fetching user datas and displaying them on the admin dashboards.

### Skills

##### 1. Creativity

Creativity was an important skill while working on my Freedom Project. Recently, I spent a lot of time designing the user interface and layout of the admin dashboard. Coming up with a design was challenging because there are many possible layouts and color schemes. I tried several different designs I decided to go with the classic sidebar layout with a black sidebar and a white content area on the right.

##### 2. How to Google

Using Google effectively was another important skill. When I have no design ideas, I searched online for dashboard inspirations. I also used [Dribbble](https://dribbble.com/search/dashboards-black-and-white) to find UI designs. Looking at other designs helped me quickly brainstorm and develop my own layout.

### Next Step

The next step for my Freedom Project is implementing the backend functionality for managing users. This includes modifying user information, banning users, and deleting user accounts. After that, I will add functionality that allows admin users to update their own account information. Once these features are complete, I will begin working on the core MVP of the project, which is allowing admin users to create and manage AI chatbots.

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
