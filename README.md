# About

This repo generates a JSON file with answers to questions on Sourcegraph's community forum [that are solved](https://community.sourcegraph.com/search?q=status%3Asolved). It uses TP and Gemini to generate [the JSON file](https://raw.githubusercontent.com/sourcegraph-community/forum-answers-for-docs/refs/heads/main/answers.json).

## Prompts

### TP

```
I want you to go to this page: https://community.sourcegraph.com/t/updating-cody-search-index-hangs-forever/2275

Grab the title: "Updating Cody search index… hangs forever"

then the answer: "I have been on this for two weeks. Now, I believe it is not directly related to Cody. I had Python Extension deactivated, and activating it fixed the problem."

Then create a json file with the following json schema:
* url
* title
* answer

Going forward I will give you a url, and you will append the next json object to the bottom of answers.json
```

#### This will produce a JSON file with the following schema

```json
{
   "url": "https://community.sourcegraph.com/t/updating-cody-search-index-hangs-forever/2275",
   "title": "Updating Cody search index… hangs forever",
   "answer": "I have been on this for two weeks. Now, I believe it is not directly related to Cody. I had Python Extension deactivated, and activating it fixed the problem."
}
```

### Gemini

```
The questions ("title") and "answer" are from a forum so the grammar and context might be off. rewrite these faqs and keep the json format.
```

#### Why Gemini?

1. Cheaper
2. It has context about Sourcegraph from a Gem (instructions)

## Publish

- Git commit
- Git push
