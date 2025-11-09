# Entry 1

##### 11/08/2025

### Choosing the Topic

In todays world, AI chatbots are super useful for learning, creativity, and just getting stuff done. But its still hard for most people to make one that really fits what they want. Most AI tools dont let you control how the bot acts or talks, and building one from scratch is extremely difficult and takes a lot of time. My freedom project this year is trying to fix that by making a easy self hosted platform where anyone can make, customize and share your own AI chatbots with just prompt engineering skills.

### Setting Up the Project & Designing the Architecture

My first step in building this project was to decide what tools I would use, plan out the features, and design the overall architecture.

For the tools, I decided to use Next.js + TypeScript for the web UI because it makes fullstack development much simpler. For the database, I chose Postgres, and for deployment I’m using Docker to make installation easier for users.

After deciding the tool, I need to design the database schema so I know how I am going to build the backend. For this part, I used a website called [prismaliser](https://prismaliser.app/). It helps me visualize my database structure while I code it, which makes planning much easier.

![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1762729725/Screenshot_2025-11-09_180809_gnxvpv.png)
![image](https://res.cloudinary.com/dyu7ogoqc/image/upload/v1762119753/prismaliser_2_llmfdf.png)

### Setting Up Docker Images for Easy Installation and Deployment

Before I actually start building the platform, I needed to set up Docker so users can install it easily, and so I can test the platform in production mode.

Since Postgres requires database migration when it's first created, I had to make sure Docker automatically runs the migrations and sets up the database when the user installs the platform. However, I've never done automatic migration inside Docker before, so I searched on google and [StackOverflow](stackoverflow.com) to see how others handle it. I found this post [How do I run Prisma migrations in a Dockerized GraphQL + Postgres setup?](https://stackoverflow.com/questions/66646432/how-do-i-run-prisma-migrations-in-a-dockerized-graphql-postgres-setup). I saw that most people just run the migration command before starting the app, so I tried implementing that myself. I also found this blog post: [Prisma Migrate: Deploy Migration with Docker](https://notiz.dev/blog/prisma-migrate-deploy-with-docker), which had a similar example of automatic database migration.

Even though I got it working, there were still some problems. The main one was that the Docker image ended up being way too big (almost 2GB). I'll need to do more research and figure out how to make it smaller later.

### Engineering Design Process

I'm currently on steps 1-4 of the Engineering Design Process. I already picked a problem to solve, came up with a possible solution, did some research to learn how others handled similar things, and started planning out how my platform will work.

I learned that making and customizing AI is hard for most people, so my goal is to make it simpler. While researching, I looked up Docker setups and Prisma migrations to understand how to handle my database. After that, I decided on using Next.js, TypeScript, Postgres, and Docker, and started planning how everything connects.

### Skills

##### 1. How to Google

Learning how to Google is one of the most important skills for any software engineer. You can't know everything or remember every single method or command, so being able to search for the right information quickly is super important. During this project, I had to look up things like Docker commands, how to automatically migrate database, and knowing how to find good answers fast saved me a lot of time.

##### 2. Problem Decomposition

When I first started this project, it feels overwhelming because there were so many parts to it. I had to figure out how to break it down into smaller steps. I started with choosing what tools to use, then worked on the database, and later focused on Docker and deployment. Doing it step by step helped me stay organized and not get lost.

### Next Step

My next step of this project is to implement authentication, and start building basic RBAC (Role-based access control) so users can have accounts and permissions. Once I have that working, I'll begin setting up a DAL (Data Access Layer) for managing user and chatbot data.

[Next](entry02.md)

[Home](../README.md)
