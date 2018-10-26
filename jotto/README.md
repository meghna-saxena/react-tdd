# Jotto - Word Guessing Game

### App Planning
- Components
  - App
    -> Title, contains children components 
  - Input
    -> Input box & submit button
  - GuessedWords
    -> Table of guessed words
  - Congrats
    -> Congratulations message 

- Redux State

| Key           | Data Type        |                             Description                             |  Starting Value  |
| ------------- |:----------------:| -------------------------------------------------------------------:| ----------------:|
| secretWord    | string           |   Word the user is trying to guess                                  | Word from server |
| success       | boolean          |   Whether or not the word has been guessed correctly                | false            |
| guessedWords  | array of objects |   Array of objects: {guessesWord: string, letterMatchCount: number} | []               |



- Where does the `secret word` come from?
  - API Server
  

1. Congrats and GuessedWords components will not be connected to redux. We can get the state from parent App component.
  - Testing w/ props
    - Hand down state from parent

  - Don't need to be connected to redux
    - Never updates state

  - Setup some common tools

2. Simple Redux
  - Work w/ `success` piece of state
  - Action creator creates `CORRECT_GUESS` action
  - Reducer updates `success`
  - Input component conditionally renders

3. More complicated redux using `redux thunk` middleware  
  - Action creators that fire off multiple acions
  - guessWord action creator
    - Add to `guessedWords` state 
    - Conditionally update `success`

4. Async action creators and axios
  - Test action creator that gets `secretWord` from server
  