---
id: 3297052e-4591-4190-9975-4e4bd30b8931
title: Zettelkasten
desc: ''
updated: 1601139466354
created: 1601139466354
stub: false
---

# Zettelkasten

## Summary

A Zettelkasten is a slip box. It was developed as a method to grow a knowledge base and produce creative works. The method was pioneered by Niklas Luhmann during his long career as a sociologist. 

## Guiding principles

Open organization rather than structured note-taking. Building a second partner for research. Encourages a "bottom-up" rather than "top-own" research methodology.

## Features

### Arbitrary Branching

### Linking
Notes in Zettelkasten are expected to be densely linked. The more densely linked the better really because it helps connect different ideas together to spawn new thoughts and contexts. 
### Registers

Registers are meant to answer the question "where do I start reading" when navigating a zettelkasten. They are pointers to the large themes in the zettel. Once an interesting line of thought is identified, you can dive into those group of notes.  
### Accidents are crucial
Working with a zettelkasten is somewhat like a conversation. You are not expected to have a detailed goal of where you'll end up each time you interact with your notes. By traversing from link to link, down the rabbit hole, your mind is expected to form connections across a diverse range of notes and ideas. Accidental traversals help greatly in finding novel connections. 

## Tools

You will want a tool with the following capabilities:

- Create links between notes.
- Create notes with static filenames. 

# Further Reading

- <https://notes.andymatuschak.org/z2QvtE9w5zs49x7WUeG8Ut1vywHDLiG2Wkm9p>
- <https://zettelkasten.de/posts/overview/>
- <https://zettelkasten.de/posts/understanding-hierarchy-translating-folgezettel/>
- <http://luhmann.surge.sh/communicating-with-slip-boxes>
- Sönke Ahrens, _How to Take Smart Notes: One Simple Technique to Boost Writing, Learning and Thinking -- for Students, Academics and Nonfiction Book Writers_, 2017.

# A Dendron-specific hierarchy and workflow

In the Zettelkasten system there really are only two types of notes, **Permanent Notes** and **Literature Notes**, the latter are used in conjunction with a system for managing bibliographies, such as BibTeX/BibLaTeX or Zotero. In addition there are transient notes which go in an **Inbox** and notes associated with **Projects** such as an article, book or conference paper. Transient notes should be archived once they are finished with. That suggests the following hierarchy:

```
+ archive
+ inbox
+ literature
+ permanent
+ project
```

As your "literature" notes may include notes on things other than books and articles, for example documentaries, podcasts, or even short biographical notes about significant individuals, `reference` may be a better top-level name than `literature`. If the author-date system of citations is the most common in your discipline you could use it for notes on books and articles, for example `reference.literature.smith.1980.md`, or perhaps just the title (or a shortened form) might do, `reference.literature.economic-dignity.md`. Notes on books could be a hierarchy of chapters, `reference.literature.economic-dignity.chap-01.md`.

As you read, you take short notes in your own words. These literature notes are your own thoughts, but their context is the work you were reading. They should include some link to your biliography management system, for example a code block at the beginning with the BibTeX/BibLaTeX entry.

The next step is to process your literature notes into permanent notes. This does not alter or destroy your literature notes, which are in fact just as permanent as your "permanent" notes. The process here is to transform your thoughts on what you have just read from the original author's context to your own context. How does what you have just read intersect or engage with your own interests and concerns? It may be that you will want to create a new note, or edit some existing notes with this new information, or perhaps break an existing note into several smaller ones. Permanent notes are largely flat in terms of hierarchy, but the beauty of Dendron is that occasionally a local hierarchy may present itself and Dendron makes it extremely easy to create those on the fly. Permanent notes are also supposed to be "atomic", that is they are a short account of one thing, idea, or concept, which is then linked to other notes to represent chains of reasoning or lines of thought. As clusters of significant topics emerge you will want to create "MOCs" -- **Maps of Content** -- which can act as high-level entry points once your notes increase in number.

Apart from using bi-directional links to forge strong connections between individual notes, it is also useful to use "tags" to create loose connections between notes. In Dendron tags are just wiki-links like all others which means that tags can also be hierarchical. This can make it easier to navigate through them if you have many. The same tags may very well apply to both literature notes and permanent notes, in which case `tag` could be another top-level in your hierarchy:

```
+ archive
+ inbox
+ permanent
+ project
+ reference
+ tag
```

What about the transient notes? The first type are the thoughts that pop into your head during the day and that you want to jot down. Dendron's "Create new scratch note" (`cmd-shift-s`) is perfect for this. In the Dendron settings, for "Default Scratch Name" set `inbox.scratch` and these notes will always be created in your inbox. These are supposed to be processed as soon as possible, either worked up into a new entry in the permanent notes, or a new research task. The inbox is also a good location for research tasks and reading lists, and Markdown checkboxes might prove useful there. Scratch notes which are upon refelection worthless could be deleted. Otherwise, once a scratch note has been processed you can use Dendron's "Archive Hierarchy" to move it to the archive (it will be created if it doesn't already exist).

After reading through your permanent notes you may identify a train of thought that is worth being worked up into an article/presentation/book. This is where the second type of transient notes come into play: project notes. Let's say that you are planning an article. You create a new note `project.article-title.md`. Because Dendron supports transcluding other notes, you can begin populating this new note with the contents of your permanent notes that you identified earlier. Once you have something looking like an early rough draft in Dendron, you can then use Pandoc or something similar to transform this into Word or LaTeX format for the final writing. Once the project is complete and accepted for publication you can again use the "Archive Hierarchy" command to move it into the archive.
