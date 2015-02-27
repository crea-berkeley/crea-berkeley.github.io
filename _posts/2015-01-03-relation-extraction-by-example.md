---
layout: post
title: Relation Extraction by Example
author: Mark Farrell
---

This post covers examples of how to extract relations (triples) from sentences and exercises to practice extracting relations from sentences. The first part of this post offers examples and exercises of what relations should be extracted from sentences, but does not offer a computational method for extracting relations from sentences. A method for extracting relations from sentences that involves pattern matching on their syntactic structure is discussed in the second part of the post. All sentences are in English.

Let's get started by discussing what relations should be extracted from sentences:

**Example** The relation walk(man, dog) should be extracted from all of these sentences:

    The man walks the dog.
    The man walked the dog.
    There is a man who walks the dog.
    The man used to walk the dog.
    The old man walks the dog.
    The man sometimes walks the dog.
    Something caused the man to walk the dog.
    The only man walked the dog.
    The man just walked the dog.
    The man will walk the dog.
    The man walked the dog quickly.
    Hmm, the man walked the dog.
    The man walked his dog.
    The man walked his dogs.
    Evidence suggests that the man walked the dog.

**Exercise** Can you think of more English sentences where walk(man, dog) is the only relation that should be extracted?

**Exercise** What relations would you extract from the following sentence?

    The man walked the dog in the park.

**Example** The relation walk_by(dog, man) should be extracted from the following sentence:

    The dog was walked by the man.

**Example** The relations walk(man, dog) and feed(man, cat) should be extracted from all of these sentences:

    The man walks the dog if the man feeds the cat.
    If the man walks the dog, then the man feeds the cat.
    The man walks the dog and the man feeds the cat.
    Either the man walks the dog or the man feeds the cat.

**Exercise** Can you think of more compound sentences where walk(man,dog) and feed(man, cat) are the only relations that should be extracted?

**Exercise** What relations should be extracted from the following sentences?

    If the man walks the dog, there is a cat who is fed by the man.
    The man walked the dog, the girl hit the baseball, and the man feeds the cat.

**Example** The relations walk(man, dog) and walk(John, dog) should be extracted from the following sentence:

    The man (John) walked the dog.

In addition, the relations walk(man, Brian) and walk(John, Brian) should be extracted from the following sentence:

    The man (John) walked the dog (Brian).

**Exercise** What relations should be extracted from the following sentence?

    The man (John) walked the dog (Brian), the girl (Sarah) hit the baseball, and John feeds the cat.

**Example** The relations walk(man, dog) and walk(woman, dog) should be extracted from the following sentence:

    The man and the woman can walk the dog.

In addition, the relations feed(man, cat) and feed(woman, cat) should be extracted from the following sentences:

    The man and the woman can walk the dog and feed the cat.
    The man and the woman can walk the dog and can feed the cat.

**Question** When extracting relations, it seems necessary to strip noun phrases of their quantifiers and qualifiers. For example, the relation walk(man, dog) should be extracted from the sentence "all blue men walk their dogs". Do you agree? Why is this?

Now let's discuss a method for extracting relations from sentences:

**Example** Extracting relations from the following sentence:

    The man walks the dog.

**Parse the sentence:**

<img src="/img/relation-extraction-by-example/1.png" width="300" />

*Assign each word in the sentence a part of speech tag:*

<img src="/img/relation-extraction-by-example/2.png" width="300" />

*Group words into phrases:*

<img src="/img/relation-extraction-by-example/3.png" width="300" />

*Group phrases into clauses:*

<img src="/img/relation-extraction-by-example/4.png" width="300" />

**Pattern match to extract relations:**

*Find clauses in the constituent tree:*

<img src="/img/relation-extraction-by-example/5.png" width="300" />

*Find predicates:*

<img src="/img/relation-extraction-by-example/6.png" width="300" />

*Rewrite the constituent tree - include the predicate:*

<img src="/img/relation-extraction-by-example/7.png" width="300" />

*Find the subject and object of the sentence:*

<img src="/img/relation-extraction-by-example/8.png" width="300" />

*Rewrite the tree to include the subject and object:*

<img src="/img/relation-extraction-by-example/9.png" width="300" />

*Relate the subject to the object:*

<img src="/img/relation-extraction-by-example/10.png" width="300" />

**Exercises**

Write software that uses this pattern matching method for relation extraction: define patterns to extract relations
from simple sentences like the one used in the example above. Use lemmatization and natural language parsing software
to assist you with this task. Refer back to the first part of the post: define patterns to extract relations from all sentences
where walk(man, dog) is only relation that should be extracted.Define patterns to extract relations from the rest of the sentences
seen in the first part of the post.

**Conclusion**

This post offered cumulative examples of relation extraction, and a computational method for relation extraction that involves
pattern matching on the syntactic structure of English sentences. It is up to the reader to complete a software implementation of this method,
and to verify that their implementation is correct with the examples provided. Feel free to ask questions and share solutions.
