# Project Name

Replace this readme with your own information about your project.

Start by briefly describing the assignment in a sentence or two. Keep it short and to the point.

## The problem

Describe how you approached to problem, and what tools and techniques you used to solve it. How did you plan? What technologies did you use? If you had more time, what would be next?

## View it livee

Have you deployed your project somewhere? Be sure to include the link to the deployed project so that the viewer can click around and see what it's all about.

# Iterations

### Iteration 01

The `greetUser` function sends a message as the bot asking for your name. This is the "start" of the bot.

Right now that function is being invoked when you load the webpage, _but_ with a delay of one second. `setTimeout(greeting, 1000)`

Try to change this to make the greeting appear faster and slower.

The `showMessage` function takes two arguments - the message, and the sender. You can pass any text as the message and either 'user' or 'bot' as the sender. This is handled with conditionals.

Try to add a `console.log` in the if statement to practise using the console.

```jsx
} else if (sender === 'bot') {
		// add a console.log here to see when it's being logged and not

    chat.innerHTML += `
      <section class="bot-msg">
        <img src="assets/bot.png" alt="Bot" />
        <div class="bubble bot-bubble">
          <p>${message}</p>
        </div>
      </section>
    `
  }
```

Also try to understand what is happening in the `<p>` tag above. what happens if you remove the `$` and the curly brackets around `message`?

When you feel like you understand the code and have added the console.logs, commit and push those changes to GitHub. Remember to write short but descriptive commit messages.

### Iteration 02

Now it's time to plan and make a decision about what kind of bot you want to build. Put a name to the bot in the HTML. As a default the bot will greet you with _"Hello there, What's your name?"_ Make sure to change this to whatever you want your bot to say.

Also think about **when** you want the greeting to happen. Maybe instead of invoking it when the website loads, you want to invoke the greeting function with a button? That's up to you.

Again, commit and push your changes.

### Iteration 03

The chatbot isn't that fun if you can't interact with it. Get the first user answer to appear and get the conversation with the bot started.

In the starter code, the first event is asking for the user's name. The starter code asks the first question from the bot, and we've got the input field in the page ready for the user to type their name. So the first task is to listen to the form being submitted, (by clicking send or hitting the enter key), and to react to it.

**We want to:**

1. Listen for the form submit event
2. When the form is submitted, post the value from the text input as a message from the user
3. Progress the app to the next question.

<aside>
💡 Remember to create small functions for different parts of your bot. This is a hint to one way of dealing with the first user input 👇 If you changed the first question to something else than asking for a name, you should name the function that handles that input accordingly.

</aside>

```jsx
const handleNameInput = (event) => {
  event.preventDefault();
  // Store the value in a variable so we can access it after we
  // clear it from the input
  const name = nameInput.value;
  showMessage(name, "user");
  nameInput.value = "";

  // After 1 second, show the next question by invoking the next function.
  // passing the name into it to have access to the user's name if we want
  // to use it in the next question from the bot.
  setTimeout(() => showFoodOptions(name), 1000);
};
```

Commit and push your changes*.*

### Iteration 04

Now you have a solid base for your bot, and the beginnings of a control flow from questions and answers, it's just to keep building up your event functions which then invoke the next question function, and to figure out the flow of your code.

Have you thought about the conversation yet? What kind of questions and answers do you want to have? Will it be typed in inputs? Yes or no with pressing buttons? A dropdown list to select from? A mix of everything? That's up to you.

Add a few more questions and answers to your bot.

Commit and push your changes.

### Iteration 05 - Optional

We want you to practice conditionals, so it's time to add some if...else statements to your bot. For example, if the user types an invalid answer they should be prompted with a message that says: _"That's not a valid answer"_ or something similar.

Check our live example bot and try out a few different answers to see the differences you get in the replies from the bot.

## Stretch Goals

So you’ve completed the blue level? Great job! Make sure you've committed and pushed a version of your project before starting on the stretch goals. Remember that the stretch goals are optional.

- Work on your CSS skills, and change the styling.
- How is the user answering the questions? Choose the form elements that you think fit the purpose best.
