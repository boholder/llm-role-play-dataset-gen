# llm-role-play-dataset-gen

> **Warning**
> The program part hasn't finished yet, feel free to take [the dataset](https://github.com/boholder/llm-role-play-dataset-gen/blob/main/data/dataset)
> if you don't want to leave with empty hands.

I want to fine-tune the locally deployed LLM to make its zero-shot chat responses have the characterization
(world view, tone of voice, perception of the user, perception of itself, etc.) I expect.
This (I hope) will eliminate the need to pass the character traits in each conversation (like what they did in [Generative Agents paper](https://arxiv.org/abs/2304.03442)).

This project is for collecting and generating such a fine-tuning dataset in [Stanford Alpaca format](https://github.com/tatsu-lab/stanford_alpaca#data-release),
which contains answers with role characteristics.

The whole process will involve a lot of manual operations. Basically it works like this:

1. This project pre-prepares dataset that contains:
2. only questions without answer:

    1. Manually input a role description.
    2. Invoke the ChatGPT API to generate answers with the role description.
    3. Manually select the answers.

3. questions with parameterized answers.

    1. Manually fill in the parameters and use program to replace them into the dataset.

4. (Optional) Invoke the ChatGPT API to generate similar derivations of
   the selected question-answer pairs to expand the training set.
   (Is this good for training? I'm not sure, can anyone tell me?)

## I need you help

* Is there a similar program readily available? I don't want to do duplicate work.

* There are never enough data, and I think the dataset will be the most valuable thing about this project.
  I'm not sure what kind of topic would characterize a character,
  maybe we'll talk about this kind of topic when we're dating or making friends?
  If you have suggestions, please give me a clue with a [discussion](https://github.com/boholder/llm-role-play-dataset-gen/discussions/new?category=ideas) or an [issue](https://github.com/boholder/llm-role-play-dataset-gen/issues).

* Is there anything we can do to make this process more automated and efficient? I want to hear from you.

* Dataset is the same content that stored in different languages,
  and synchronization of content between dataset should be maintained.
  This involves manual translation work and content management.
  It is theoretically possible to automate the tagging of changed content using GitHub Actions.
  Synchronization is based on English version.

* Perhaps this project should be paired with a sister project that creates a knowledge base
  representing the character's world view, if the character is a fictional one who living in a fantasy or SF world.
  But let's make **this** project ready first.