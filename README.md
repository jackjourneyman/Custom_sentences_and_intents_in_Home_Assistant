# Custom sentences and intents in Home Assistant

Custom sentences and intent scripts are an alternative to automations for controlling voice assistants. 

The custom sentence acts as the trigger. It passes parameters to the intent script, which carries out the required actions and plays the TTS resonse.

You can use them to extend and personalise Home Assistant's built-in sentences, or to send the TTS response to a speaker other than the one in your voice assistant. Sentences can be marked up with alternate phrases and words that may be omitted, and values passed to the intent script can be tightly controlled. The scripts support templating.

Here are some simple, practical examples of what you can do, including setting timers and alarms and managing shopping lists.
   
The examples are quite modular - everything doesn't have to be crammed into the intent. Templates can be used to construct common phrases that can be repeated in different places. Scripts can be used to carry out common actions, and these may be easier to maintain, particularly if you prefer to use the UI.

To use intent scripts you have to install the [intent script](https://www.home-assistant.io/integrations/intent_script) integration.

Please make comments and suggestions in the [discussions page](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/discussions)

----------------------------------------

## Index

[The basics](https://github.com/jackjourneyman/Custom_sentences_and_intents_in_Home_Assistant/blob/main/the_basics.md)

### Intents

[Alarm clock](https://github.com/jackjourneyman/Custom_sentences_and_intents_in_Home_Assistant/blob/main/alarmclock.md)

[Calendar](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/calendar.md)

[News headlines](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/news_headlines.md)

[Shopping lists](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/shopping_list.md)

[Speaking clock](https://github.com/jackjourneyman/Custom_sentences_and_intents_in_Home_Assistant/blob/main/speaking_clock.md)

[Timers](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/timers.md)

[World clock](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/world_clock.md)

### Scripts

[Speaker script](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/speaker_script.md)

### Templates

[Random phrases](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/random_phrases.md)

[Weather](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/weather.md)

### Resources

[Documentation](https://github.com/jackjourneyman/Custom_sentences_and_intents_in_Home_Assistant/blob/main/documentation.md)

[My voice assistant is slow](https://github.com/jackjourneyman/Custom_sentences_and_intents_in_Home_Assistant/blob/main/voice_assistant_speed.md)

[Tools and shortcuts](https://github.com/jackjourneyman/Custom_sentences_and_intents_in_Home_Assistant/blob/main/resources.md)

[Wrinkles](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/wrinkles.md)

[Home Assistant Index](https://jackjourneyman.github.io/homeassistantindex/index.html)

[Home Assistant Cookbook](https://community.home-assistant.io/t/the-home-assistant-cookbook-index/707144)

----------------------------------------------

## Speakers

By default Assist responds to built-in commands through the voice assistant that heard the command. This is difficult to change short of hacking the voice assistant device itself. (If your voice assistant is an ESPHome device there are some [configuration tools](https://esphome.io/components/voice_assistant.html).)

This is one reason for choosing to use custom sentences and intents - the response can be played through any speaker you like.

The examples in this repository call a [script](https://github.com/jackjourneyman/custom-sentences-and-intents-in-Home-Assistant/blob/main/speaker_script.md) to deliver TTS sentences.
```
    - action: script.tts_response
      data:
        tts_sentence: "Whatever you need to say..."
```
You can substitute your own script, of if you want responses to come through your voice assistant you can simply use ```speech```:
```
    speech:
      text: Whatever you need to say...
```

