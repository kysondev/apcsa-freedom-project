# Tool Learning Log

## Tool: NextJS, TypeScript, PostgreSQL, Redis, Prisma, Kysely, Docker

## Project: BuildLLM (buildllm.chat)

Description: A self hosted platform where users can create their own AI chatbots by choosing a base model (ex. gpt, claude, deepseek), customizing it with prompt engineering, and publishing it for others to use. They can also add a custom knowledge base.

---

### 10/5/2025:

- Today I set up a separate [github repo](https://github.com/kysondev/buildllm) for my BuildLLM project and installed Next.js along with the main tools I’ll be using, like Prisma, Kysely, and Docker. Prisma will handle the database schema, and Kysely will be my query builder since it’s faster and simpler for queries. I also made a basic Docker and Docker Compose setup that I can use later for production.

![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1759713853/Screenshot_2025-10-05_211337_g58jik.png)

- One challenge I ran into was figuring out if I should make the project a monorepo so I can separate the admin panel and user panel later. I also wasn’t sure if I should run the database inside the Docker container or keep it separate to let user connect to a separate database on another server. (I decided to put them all together)

- Another thing I spent some time on was deciding whether to use ShadCN for the UI. I ended up choosing to use it because it’ll save me a lot of time designing components from scratch, especially since I don’t have a lot of time this year.

Links I used today:

- [Next.JS Docs](https://nextjs.org/docs)

My next step is to design the database and then the UI in figma before I dive into the actual code. For the database I will be using PostgreSQL as the primary database and most likely Redis as a secondary database depends on if I need caching. For the design I think I am going for minimalistic dark theme.

### 11/2/2025:

I found this website: [prismaliser](https://prismaliser.app/). It lets you visualize and design Prisma database schemas. I used it to make the basic structure for my freedom project.

I’ve learned that planning the database early really matters. In past projects I usually skipped this step and ended up having to redo a bunch of things later. This time, I’m trying to design it properly from the start before everything else.

I also implemented automatic database migration when the user installs the app through Docker. Normally I run migrations manually, but I wanted to make setup as simple as possible, like running a single command to get everything running. I have never done automatic migrations before, so this was new to me. It took me some time to get it to work, but it works now.
![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1762119753/prismaliser_2_llmfdf.png)

Although the Docker image size is a bit too large (~1.8 GB), that’s something I’ll need to fix later.

![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1762126922/Screenshot_2025-11-02_184121_to9ykc.png)
![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1762126924/Screenshot_2025-11-02_184131_x91mct.png)

Next, I’m going to work on adding authentication. I want to make sure users can register and log in properly before I start focusing on the UI or the actual features.

<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
