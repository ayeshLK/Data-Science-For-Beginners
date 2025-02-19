# Contribute by translating lessons

We welcome translations for the lessons in this curriculum!

> Note, please do not use Google Translate or other machine translation tools for translations, but rather use your own proficiency and manually translate the files.

## Guidelines

There are folders in each lesson folder and lesson introduction folder which contain the translated markdown files.

> Note, please do not translate any code in the code sample files; the only things to translate are README, assignments, and the quizzes. Thanks!

Translated files should follow this naming convention:

**README._[language]_.md**

where _[language]_ is a two letter language abbreviation following the ISO 639-1 standard (e.g. `README.es.md` for Spanish and `README.nl.md` for Dutch).

**assignment._[language]_.md**

Similar to Readme's, please translate the assignments as well.

**Quizzes**

1. Add your translation to the quiz-app by adding a file here: https://github.com/microsoft/Data-Science-For-Beginners/tree/main/quiz-app/src/assets/translations, with proper naming convention (en.json, fr.json). **Please don't localize the words 'true' or 'false' however. thanks!**

2. Add your language code to the dropdown in the quiz-app's App.vue file.

3. Edit the quiz-app's [translations index.js file](https://github.com/microsoft/Data-Science-For-Beginners/blob/main/quiz-app/src/assets/translations/index.js) to add your language.

4. Finally, edit ALL the quiz links in your translated README.md files to point directly to your translated quiz: https://witty-beach-04b13e603.1.azurestaticapps.net/quiz/1 becomes https://witty-beach-04b13e603.1.azurestaticapps.net/quiz/1?loc=id

**THANK YOU**

We truly appreciate your efforts!
