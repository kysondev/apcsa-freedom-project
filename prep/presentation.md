# Presentation Plan

## Hook

- Has anyone ever emailed a teacher late at night and hoped they would respond? It is very realistic and that is definitely not happening. But what if teachers could still answer questions at 2am without actually being awake? That is the problem I want to solve.

## Product

- Overview: A self-hosted (Docker based) platform for building and deploying custom AI chatbots with prompt engineering and knowledge bases.
- People can create their own chatbots and customize it with RAG and prompt engineering.
- Video Demo: [Link](https://youtu.be/OWh33o4rchM)
- Project Code: [Github Repo](https://github.com/kysondev/typepanel)

## Process

- Started by planning out the project architecture and then work on the layout of the website
- Built admin panel and user authentications to create and manage chatbots
- MVP: built RAG from scratch with TypeScript and knowledge base creation
- Key Challenge: Making AI responses accurate using custom data from knowledge base instead of generic answers
- Finished off MVP by building the chat page for users to actually use the chatbots

## Conclusion

- Key takeaways:
  - This project shows that AI is more useful when you can control it.
  - The hardest part when it comes to building a software wasn't one feature, but connecting everything (AI and Database).
  - Designing the database and architecture early saved time and prevented major issues later.
- Closing: AI won't replace teachers, but tools like this can make their help available anytime.

<!-- EXAMPLE

## Hook
* Verbal riddle of GGD

## Product
* GIF/Demo of example/non-example

## Process
* Flowchart of plan
  * MVP: noun -> door -> yes/no
  * Beyond MVP: noun -> word relation API -> noun API -> yes/no, with counterexample
* Code snippets of:
  * MVP
  * Both APIs
  * Challenge with API keys

## Conclusion
* [URL to project]
* Takeaways
  * Less = more: the heart of the riddle was one line of code; it obviously took more to make the entire thing work, but one complicated line of regular expressions was essentially the solution to the riddle
  * Expect the unexpected: it’s important to budget time for things you don’t account for; for example, I didn’t consider the fact that I would need another entire API to detect nouns
  * Determination is key: ironically enough, I had to make my API keys private. At first, it didn’t seem like it was possible, which meant I couldn’t publish my app. But after all of that hard work, I was determined to find a solution, and I found it in config variables.
* "Presentation can’t, but a speech can"


-->
