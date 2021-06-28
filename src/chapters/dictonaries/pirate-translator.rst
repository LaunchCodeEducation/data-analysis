Code Like a Pirate!
===================

In this chapter, we have learned how to define a dictionary, add or modify the
key/value pairs, search through the keys and values, and loop through the
collection. However, we still need to understand what dictionaries allow us to
*do*.

Lists vs. Dictionaries
----------------------

First, neither collection is better than the other. They are just different.
There are some problems that lists solve more easily, while dictionaries are
the better choice for other tasks.

The question isn't which collection is *better* than the other. The proper
question is which data structure best *fits the job at hand*.

Let's take a look at one task where using a dictionary really helps.

Translation App
---------------

Google provides an easy-to-use algorithm that translates simple words and
phrases between languages.

.. figure:: figures/translation.gif
   :alt: Gif showing Google translate the word "Hello" into different languages.

   `Google translate <https://translate.google.com/>`__

While we cannot build something as complete as this app (yet), we CAN
understand how to make something similar with Python. At its core, the program
is built around a dictionary!

Take a look at this small English-to-Spanish dictionary. The keys are English
words, and the values are the same words in Spanish:

.. sourcecode:: Python
   :linenos:

   eng_to_span = {
      'hello' : 'hola',
      'blue' : 'azul',
      'apple' : 'manzana',
      'python' : 'pitón',
      'library' : 'biblioteca'
   }

Now imagine that a user inputs an English word. We can easily search the keys
in the ``eng_to_span`` dictionary for that word. If we find it, we can print
the value for that key, which is the Spanish translation.

That's it! Our word translator is limited only by the size and accuracy of the
dictionary.

.. admonition:: Try It!

   Add key/value pairs to the ``translate`` dictionary! Feel free to use words
   from any two languages you want, but you must be able to type in the starting
   words with the letters on your keyboard.

   #. The keys in the dictionary should be in the language that the user
      enters.
   #. The values will be in the other language.
   #. Use Google translate if you need help finding word pairs.

   .. raw:: html

      <iframe src="https://trinket.io/embed/python3/1aa8392d55" width="100%" height="500" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Walking through the code:

#. ``keep_going = True`` keeps the ``while`` loop running until the user tells
   the program to stop.
#. The ``word_to_change`` input statement prompts the user for the word to
   translate.
#. ``if word_to_change in translate`` checks to see if the entered word is one
   of the keys in the dictionary.

   a. If ``True``, then ``print(translate[word_to_change])`` displays the value
      for the key.
   b. If ``False``, then the user sees a message telling them that their word
      is missing from the dictionary.

#. The ``repeat`` input statement asks the user if they would like to keep
   going. Any entry that does NOT start with ``'y'``
   (``repeat[0].lower() != 'y'``) sets ``keep_going`` to ``False``, and the
   program ends.

.. admonition:: Note

   We *could* build the translation app with lists, but that code would be less
   efficient and more likely to have bugs.

   Explain why.

Talk Like A Pirate
------------------

Once we complete a language-to-language dictionary, we can use it to translate
more than just single words. Earlier in this chapter, we created a dictionary
that linked words in pirate-speak with their English meanings. Let's use this
to have a little fun!

Our next task will take a set of text and replace some of the English words
with pirate-speak. Follow the instructions listed below the editor to complete
the program. You can also see the steps by clicking the *Instructions* tab in
the editor.

.. raw:: html

   <iframe src="https://trinket.io/embed/python3/33642cab22" width="100%" height="500" frameborder="1" marginwidth="0" marginheight="0" allowfullscreen></iframe>

**Instructions:**

#. Note that the English-to-pirate dictionary is defined in the
   ``translate.py`` module.
   
   a. Placing it here is an excellent idea, because we can keep multiple
      dictionaries in ``translate.py`` and then import only the ones we want
      into different programs.
   b. Changes made to a dictionary in ``translate.py`` get applied to all
      programs that import it.
   c. Feel free to add, remove, or edit the key/value pairs in
      ``eng_to_pirate``!

#. Line 3 assigns the string we want to translate to the ``text`` variable, and
   line 4 splits ``text`` into a list of separate words. Line 6 defines an
   empty list to hold the words that go into the translated string.
#. On line 7, set up a ``for`` loop to iterate through the list of words:

   .. sourcecode:: python
      :lineno-start: 7

      for word in eng_words:

#. Now set up a conditional to check if ``word`` is a key in the
   ``eng_to_pirate`` dictionary. If ``True``, append the *value* for the key
   to the ``new_words`` list. If ``False``, append the original word.

   .. sourcecode:: python
      :lineno-start: 8

         if word in eng_to_pirate:
            new_words.append(eng_to_pirate[word])
         else:
            new_words.append(word)

#. After the loop is done, join the elements from the ``new_words`` list into
   a new string, then print the result.

   .. sourcecode:: python
      :lineno-start: 13

      new_text = ' '.join(new_words)
      print(new_text)

#. Now run the program, fixing any syntax, runtime, or logic errors. Properly
   done, the output should look like:

   ::

      If ye be interested in tales with happy endings, ye would be better off reading some other book.

Nice! Feel free to change the value of ``text`` to try out different
translations.

.. admonition:: Note

   Right now, our translation program does NOT consider case or punctuation.
   We will fix this in the sections below.

Consider Case
^^^^^^^^^^^^^

Change ``you`` to ``You`` in the text and run the program again. Notice that
it leaves the capitalized word alone. All of the keys in ``eng_to_pirate`` are
lowercase strings, so ``You`` isn't found.

Let's add some logic to deal with capitalized words:

#. Change the ``if`` statement to search for ``word`` in lowercase. Note that
   we also need to update the first ``append`` statement:

   .. sourcecode:: python
      :lineno-start: 8

      if word.lower() in eng_to_pirate:
         new_words.append(eng_to_pirate[word.lower()])

#. Run the program again, and note that ``You`` gets changed to ``ye``.
   This is better, but not quite complete. The next fix is to replace
   capitalized words with capitalized translations.
#. Change the ``if`` statement one more time to also check if ``word`` starts
   with a capital letter. If ``True`` we can retrieve the translated word and
   then apply another string method to capitalize it.

   .. sourcecode:: python
      :lineno-start: 8

      if word.lower() in eng_to_pirate and word[0].isupper():
         new_word = eng_to_pirate[word.lower()]
         new_words.append(new_word.capitalize())

#. Run the program again. Woo, hoo! ``You`` translates to ``Ye``! But wait,
   now nothing else in ``text`` gets converted! The way the ``if`` statement
   works now, only capitalized English words get changed.
#. To fix this, add an ``elif`` statement to bring back the original check and
   translation statements:

   .. sourcecode:: python
      :lineno-start: 11

      elif word in eng_to_pirate:
         new_words.append(eng_to_pirate[word])

Our program now replaces both lowercase words and capitalized words.

Final Touch
^^^^^^^^^^^

When we split ``text`` into a list of separate strings, punctuation marks
remain attached to the words. Since the keys in the ``eng_to_pirate``
dictionary don't include punctuation, strings like ``'Stop!'`` remain the
same.

We won't step through building the code like we did above. Instead, here is
one way to deal with periods, commas, and exclamation points. Feel free to
paste this into your code above:

.. sourcecode:: python
   :lineno-start: 7

   for word in eng_words:
      punctuation = '' # Start 'punctuation' as the empty string.
      
      # Check if 'word' ends with a period, comma or !
      if word[-1] == '.' or word[-1] == ',' or word[-1] == '!':
         punctuation = word[-1] # Save the punctuation mark.
         word = word[:-1]       # Reassign 'word' WITHOUT the mark. 
      
      if word[0].isupper() and word.lower() in eng_to_pirate:
         new_word = eng_to_pirate[word.lower()] # Translate 'word'.
         
         # Append 'new_word' combined with any saved punctuation mark.
         new_words.append(new_word.capitalize() + punctuation)
      elif word in eng_to_pirate:
         # Append translated word plus any saved punctuation mark.
         new_words.append(eng_to_pirate[word] + punctuation)
      else:
         # Append original word plus any saved punctuation mark.
         new_words.append(word + punctuation)

Try entering different phrases for ``text`` to check that the punctuation and
capitalization code works.

.. admonition:: Examples

   #. **Text:** ``"Stop! Go Meet The Principal in the cafeteria."``

      **Translation:** ``"Avast! Go Meet Th' Scallywag in th' swill dungeon."``
   #. **Text:** ``"Put away your phone and focus on the computer!"``

      **Translation:** ``"Put away yer cursed device and focus on th' magic
      box!"``
   #. **Text:** ``"Listen to your teacher."``

      **Translation:** ``"Listen ta yer wise sage."``
