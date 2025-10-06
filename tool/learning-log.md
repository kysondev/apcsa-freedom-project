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

<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
