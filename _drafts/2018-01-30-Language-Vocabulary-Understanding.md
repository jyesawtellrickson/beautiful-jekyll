Language apps are a prime place to implement AI features, what better to help the brain learn than another brain? The most recent product I've seen doing this is Duolingo with their language bots that allow you to practice language with a 'person' [https://mashable.com/2017/11/28/microsoft-learn-chinese-app/#iUU_CvE82aqU]. This is neat but what I want to focus on today is simple vocab learning. This is something which is common across most apps but something I've seen done wrong so often. Words that you've learned keep repeating themselves or some words just never appear when you obviously need to practice. And sometimes it's very easy to guess based on process of elimination for the other words.

Current models seem to assign certain features to words, some example ones that I could think of are:
 - word recency (last time it appeared)
 - word accuracy (how often it is correct)
 - combination of recency and accuracy (how many correct out of last 5 attempts)

However, it would be nice if we could do more. We can make things more difficult by showing words which are similar. We could use clustering models for words (word embeddings?) to see which words are similar to others, or compare to words that we know the user doesn't know well.

Similarly, we could use clustering on word meanings and the like to create lessons that focus on different things, such as verbs about the arts.

Maybe we could also predict the likelihood that users know certain words and use this to decide which words to show. This model could be based on the features described above, but we can train it as a sort of q-learning model which gets a higher score when the user doesn't immediately get the answer correct.
