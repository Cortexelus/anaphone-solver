# anaphone-solver

Algorithm and web UI for solving anaphones (phonetic anagrams). [\[play with it\]](http://anaphonr.appspot.com)

# What is an anaphone?

A rearrangement of the sounds (phonemes) of a word/phrase to make a new word/phrase. 

Examples
  * *lucky gas* : *galaxy*
  * *philosophy* : *awful fussy* 
  
# Algorithm

An existing anagram solver can be adapted to solve phonemes by building a custom dictionary. There are 39 phonemes in the [CMU pronouncing dictionary](http://www.speech.cs.cmu.edu/cgi-bin/cmudict). I give each a single ASCII character (see `encode_word`). I build a new dictionary in `build_dictionary` by cross-referencing a scrabble dictionary with the CMU pronouncing dictionary. The anaphone format of the new dictionary files look like this:

```
D0LO;EV  cartel's
D0LO;L1  cartera
D0LO<  karter
D0LO<  carter
D0LO<;OM  carteret's
D0LO<AO  carteret
D0LO<V  carters
D0LO<V  carter's
D0LO<VSAE  cartersville
D0LOA9  carted
D0LOAH  carting
D0LOB  carty
D0LOB  cartee
D0LOB<  cartier
D0LOBW1G  cartesian
```

* `TWL06.txt`: scrabble dictionary of commonly used words
* `common_combo_dictionary.txt`: intersection of scrabble and cmu dictionaries in anaphone format.
* `combo_dictionary.txt`: cmu dictionary in anaphone format.
* `simple_combo_dictionary.txt`: simple dictionary in anaphone format used for debugging

Python anagram solver was adapted from [this code](http://stackoverflow.com/questions/55210/algorithm-to-generate-anagrams). See more [here](https://github.com/Cairnarvon/anagram) for visual explanation of depth-first search. 

# This repo

Contains backup of Google AppEngine source code. Originally created at HackNY 2012. 

# Todo

* Write the algorithm in C to be way faster
* White-listing UI can be improved with fast *narrowing down* -- essential for writing efficiently
* Credit the man who inspired me to work on this project, I have forgotten his name. 
