# Simple Dialogues

> lanzhang76 & annagarbier


## Summary
A 'novel', made for NaNoGenMo 2020. Even simple dialogues are complicated.


## Preview

```
Raymond approaches the counter.

Raymond raises the tip of his tongue against his gum line,
just behind his top teeth. He releases air through his mouth,
creating slight vibrations between his tongue and gum line.
He touches his lips together. With his vocal folds tensed,
he releases air through his nasal cavity. He rounds his lips
so that they create a small opening. With his tongue in a
relaxed position at the back of his mouth, he tightens his
vocal folds and releases air through his mouth. He raises
the tip of his tongue against his gum line, just behind his
top teeth. Keeping his tongue firmly in this position, he
tenses his vocal folds and releases air so that the air moves
across the sides of his tongue.He touches the tip of his tongue
to the roof of his mouth at his gum line, just behind his top
teeth. He creates a tight constriction and allows air pressure
to build inside his mouth. He quickly lowers his tongue, releasing
the air pressure in a short burst. As he does so, he keeps his
vocal folds tense. He raises the blade of his tongue towards
his gum line, just behind his top teeth, without actually
touching the roof of his mouth. With his vocal folds tensed,
he releases air through his unconstricted mouth. He moves his
tongue so that it almost touches the middle of the roof of
his mouth, but don't create a constriction. He tenses his
vocal folds and pushes air through his mouth. He closes his
lips together. He pushes a little air into his mouth, so that
air pressure builds behind his lips. He quickly parts his lips,
releasing the air pressure in a short burst.He closes his lips
together. He pushes a little air into his mouth, so that air
pressure builds behind his lips. He quickly parts his lips,
releasing the air pressure in a short burst. He raises the tip
of his tongue against his gum line, just behind his top teeth.
Keeping his tongue firmly in this position, he tenses his vocal
folds and releases air so that the air moves across the sides of
his tongue. He raises his tongue and he moves it close to the
middle of the roof of his mouth, without creating a constriction.
He tenses his vocal folds and pushes air through his mouth.
He raises the tip of his tongue against his gum line, just
behind his top teeth. With his vocal folds tensed, he releases
air through his mouth, creating slight vibrations between his
tongue and gum line.

    RAYMOND:  "Small drip please."
```


## Full text
* [Full text output](https://raw.githubusercontent.com/annagarbier/simple_dialogues/master/novel.txt)


## Source code
* [Notebook](https://github.com/annagarbier/simple_dialogues/blob/master/generate.ipynb)


## Implementation notes

1. We hand-write very simple dialogue data. E.g.:

```
{
    "title" : ["INT.","Mud Coffee Shop", "7:00AM"],
    "prologue" : "Raymond approaches the counter.",
    "dialogue" : [
        ["Raymond", "he", "his", "Small drip please."],
        ["Barista", "she", "her", "Cream or sugar?"],
        ["Raymond", "he", "his",  "Small drip please."],
        ["Barista", "she", "her",  "Your name?"],
        ["Raymond", "he", "his",  "Raymond."],
    ],
    "epilogue" : "The barista nods, reaches for a cup, and begins his order."
}
```

2. Our script takes the data as input, and outputs prose. Specifically, the script:
    * Gets a phonemic description of each word in the dialogue (e.g. `small` -> `S M AA1 L`) using `nltk`'s `pronouncing`. 
    * Converts each phoneme in the dialogue into a description of vocal tract movements (e.g. `S` -> `Raymond raises the tip of his tongue against his gum line, just behind his top teeth. He releases air through his mouth, creating slight vibrations between his tongue and gum line.`) using a hand-written phoneme-to-description mapping.
    * Adds a little narrative text and formatting around the generated content.