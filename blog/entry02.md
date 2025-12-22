# Entry 2

##### 12/21/2025

### Content: Progress I Have Made & Goals for Winter Break

Over the past month, I've made some progress on my Freedom Project ([TypePanel](https://github.com/kysondev/typepanel)). I set up the basic authentication system and data access layers for user related services. For authentication, I discovered a TypeScript framework called [Better-Auth](https://better-auth.com/). It made authentication easy to set up while maintaining best security practices.

I also worked on the authentication page UI. I decided not to use a UI library like [Shadcn](https://ui.shadcn.com/) and just built the components myself with [TailwindCSS](https://tailwindcss.com/). It gave me more freedom to style things the way I wanted. I chose black as the primary color because it keeps the layout clean and minimal.

![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1765145803/Screenshot_2025-12-07_171548_dr19yi.png)
![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1765145846/Screenshot_2025-12-07_171710_zdl38h.png)
![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1765145910/Screenshot_2025-12-07_171817_bq50qn.png)

For the Google and GitHub buttons, I originally planned to download the icons manually, but that felt unnecessary and cluttered. After looking around, I found a small icon library called [Developer-Icons](https://xandemon.github.io/developer-icons/), which includes many popular logos and works well in React.

On December 14th, I created a separate page for admin account creation. This page is intended for first time setup when users initially install the platform and need to configure an admin account.

![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1765757890/Screenshot_2025-12-14_191723_p0fdv5.png)

When deciding how to handle database queries, I found [Kysely](https://kysely.dev/), which is a query builder that doesn't add much overhead to SQL query like [Prisma](https://www.prisma.io/). I decided to use Kysely as my main way to query the database, while still using Prisma for building and migrating the schema.

For winter break, my main goal is to implement the actual admin account creation flow. Currently, the UI exists but has no functionality yet. Since no other features can be properly implemented without user accounts, this is my top priority. If time allows, I also want to start building an admin panel UI and begin working on the chatbot page.

### Engineering Design Process

I am currently on Step 5 of the Engineering Design Process, which is prototyping. At this stage, I have built a basic authentication system and several initial pages. My next goal is to implement the admin user creation flow so that I can move on to Step 6: testing the prototype. I hope to reach this stage during winter break.

### Skills

##### 1. Organization

Organization is an essential skill, especially as the scale of a project grows. For this project, I decided to use a feature/domain based architecture. This approach helps keep files structured by functionality rather than by type, making the project easier to maintain and more scalable in the future.

##### 2. Logical reasoning

At the current stage of development, logical reasoning is a really important skill. I need to carefully plan how different parts interact with each other. I realized that making sure the account creation and admin setup flow works correctly is critical, since all other features depend on users being able to create and manage accounts. Strong logical reasoning skills have helped me identify this priority and plan for the future.

### Next Step

My next step for this project is to implement the admin account setup flow during winter break. Once that is complete, I hope to officially begin working on the core MVP of the project by implementing chatbot creation. I plan to take this process step by step, starting with account creation before moving on to other advanced features.

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
