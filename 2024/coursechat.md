# Implement an AI Course Chat

## Administrative

- Supervisor: Leander Jehl
- Contact: <leander.jehl@uis.no>

## Project Description


The goal of this project is to implement an AI based chatbot for the DAT310 Web programming course.
The envisoned design is a bot that can pick up prompts from a public discussion on the courses discord channel, and reply with course related information.
The goal is to build a bot using the publicly available Petals system [1].

The main task is to implement a Petals clients, that integrates with a discord bot.
Additional tasks are related to the usability of the bot. 
This includes a strategy to rate limit questions on discord, as well as possibly to include course content as context into questions to allow more precise or specific answers.

## Tasks

- Study how to create a discord application, that can receive and reply to questions.
- Investigate Petals interface, and come up with a plan to integrade a client into the discord bot.
- Implement initial bot, test and improve usability.

## Resources

[1]: https://petals.dev/
