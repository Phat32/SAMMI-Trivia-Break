# SAMMI-Trivia-Break

A Trivia game to play with stream, created to be used while running an ad break so the viewers with ads don't miss out on the action

![image](https://user-images.githubusercontent.com/10120690/197626125-a047b0dc-f4ae-4b2e-b1eb-98f124e0ee7a.png)

# Required Extension

[String Parser](https://github.com/Phat32/SAMMI-String-Parser) by *Phat32*

[Move Transition](https://obsproject.com/forum/resources/move-transition.913/) by *[Exeldro](https://github.com/exeldro)*

# Installation

Pressing **OBS Setup** will create a new scene with all the required sources and effects applied.

![image](https://user-images.githubusercontent.com/10120690/197630222-b2c14022-ba58-4689-8df0-f26580e2f165.png)

# Configuration

Open Setting Button

- RunCommercial [bool] - Runs an ad on Twitch when the timer starts counting down
- Seconds [int] - How long to run the trivia for
- FontName [string] - The name of the font you want to use

![image](https://user-images.githubusercontent.com/10120690/197626661-7ef6e196-f4f7-4897-8966-242b3857a58e.png)

**NOTE**
If running commercials it is required to set the Seconds to one of the set commercial runtime values for ads to run properly

Allowed Values:  30 | 60 | 90 | 120 | 150 | 180

![image](https://user-images.githubusercontent.com/10120690/197626855-3163009f-ef21-4736-ba60-3ef8d08dc718.png)

**AT LEAST 1 CATEGORY IS REQUIRED**

Go to [Open Trivia Database](https://opentdb.com/api_config.php) and select a category you want to pull from and generate the URL by pressing the button at the bottom.
Take the value from category parameter of the URL and add it to the Array

![image](https://user-images.githubusercontent.com/10120690/197627556-9aff3be5-21c7-4f61-bc15-7ea146e1b44c.png)

Freely edit the Show and Hide Trivia buttons to customize how the effect is displayed and hidden from the audience. Fading the answers while the timer runs is locked.

# Usage

Pressing **Run Trivia** will kick off the whole show!

First it will call out and get the trivia, which can be delayed at times if the API gets busy, and once obtained will trigger the **Show Trivia** button and the count down above the Run Trivia button.

The countdown will start letting you know how long until the ad runs (if confugured to do so) and when the main timer starts. While this happens the question is set and the answers are randomly assigned to an answer slot.

![image](https://user-images.githubusercontent.com/10120690/197629922-2a1aee60-70e7-4030-9bb5-8cc51d6a0089.png)

The question will first fade in and give a pause allowing you to read it out, then fade in all 4 answers at once with a pause again to allow for reading. The timer will finally fade in and start when the Countdown concludes.

During the halfway point of the timer the first incorrect answer will randomly fade away, then again with 1/4 left to go. When the timer concludes the final wrong answer will fade way long with the timer leaving just the answer and question for a brief period allowing for reaction and for those viewing commercials to see the answer.

![image](https://user-images.githubusercontent.com/10120690/197630084-9218d6c4-5b87-4686-9f4d-3cbd062aa24b.png)

Lastly the **Hide Trivia** buttom will be triggered to conclude the interactions.

If you press the button by accident or need to end the trivia right away cause something is happening, pressing **End Now** will immeditaly stop the trivia in action and active the **Hide Trivia** Button
