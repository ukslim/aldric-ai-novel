# aldric-ai-novel

An experiment in producing AI slop literature

*The Digital Librarian*, is a novel by Claude Sonnet 4, it is not my work.

I was curious what I'd end up with if I gave the LLM nothing but a premise and a
process. I would add no creativity of my own, nor editorial feedback - I would
just facilitate the process as mechanically as I could.

The whole effort probably took about 2 hours of compute time, slowed down by
waiting for its human to do the next part of the process.  This *could have*
been made into an entirely unattended script. I'm certain someone has done so.

Collating the materials into this Git repository took longer than the sum
total of interaction with Git (I could have avoided this by doing the work
in an environment like Cursor, or by scripting against the Claude API).

It would be incredibly simple to write a bot that writes dozens of "novels" of
this standard per day, and publishes them to Amazon or whatever (I don't know
whether ebook platforms have any guards to prevent this). It has always been
difficult for consumers to find wheat among the chaff of published literature.
The capability demonstrated here *massively* increases the potential for more
chaff.

## The outcome

I haven't read it, properly, yet - and there's a likelihood I never will. I have
real books to read! But I've skimmed it enough to get its measure, and in the
process of creating it I've seen plot summaries and know where to skim-read.

It is, absolutely, AI slop and reading a proper novel is better use of your
time.

Logic dictates that it can't contain a single original idea. Yet who knows, 
perhaps there's something in the remixing of pre-existing ideas in there that
would be new to some reader or another. I'm sure human-written novels have been
written with no original ideas either.

Superficially, it has every appearance of a real novel. It follows a very
traditional structure - another AI tells me that the chapter outline seems to be
based on a hybrid of well-established screenplay/novel planning frameworks.
Print it, put it in a bookshop, and it might pass as the real thing until a
customer takes it home and reads it with proper attention.

Once you read it with any attention, although it seems to start OK, 
it soon collapses into incoherence. The continuity between chapters
is broken (possibly an artifact of how the draft was written and revised
chapter-by-chapter -- although it always had the opportunity to refer
to other chapters). It repeats itself, making it a really boring read, 
even though the "revision" draft claimed to reduce that.

The plot seems to make sense at inception, but by the time it makes
it to the page it's nonsensical and also, really dull. I think you could
probably identify the "beats" referred to in the plans, but there's no way
you can make yourself care about them.

It has plenty of AI weirdness. There's a bonkers bit of discontinuity about a phone ringing, early on.
The intermediate documents, and Claude's chat as
it edits, keeps referring to a "Tom and Maggie romantic B-plot" - but no
romantic scene ever materialises, not a kiss or a hug or a romantic whisper.
Then in the epilogue they are engaged!

A while ago, an AI writing prose was like a dog walking on its hind legs "It is
not done well, but you are surprised to find it done at all!". I think we are
still in that territory, but the gap is closing. I also think that if you make
allowances, it's possible to read this with a degree of pleasure - in the same
spirit as watching a dog walking on its hind legs.

## How it was made

I asked for some ideas for subject matter, based on "person with some
personality trait, thrown into circumstance that conflicts with that personality
trait", and Claude offered me:

 - A vegetarian chef inherits a prize-winning butcher shop 
 - A claustrophobic woman becomes the lighthouse keeper on a remote island
 - A technophobic librarian discovers the town's ancient library is actually run
   by artificial intelligence
 - A colour-blind artist is commissioned to restore the village's famous rainbow
   mural
 - A chronic insomniac takes a job as a sleep therapist

I picked the AI theme, since it was pleasingly meta. My **only** other editorial
input was:

> Aim to end each chapter on a cliffhanger -- what will someone do? what did
> they see that shocked them so much? All the better if the answer comes not in
> the next chapter, but in another chapter not long after.

... in an effort to produce something a little bit Dan Brown.

The process is:

  + from the concept, write a treatment
  + from the treatment, write a detailed plot
  + from the plot, write a chapter outline
  + from the artifacts so far, write a detailed profile of each character
  + from the artifacts so far, write a step-by-step plan for writing the book
  + follow that plan to the letter

Everything was done in the Claude.ai chat interface, in a "project", adding
documents to the "project knowledge" as they were produced.

The plan it produced was a sort of "waterfall method" of novel building - and
describes itself as a 30 week plan!

All of these intermediate documents are in the `intermediate-artifacts` directory
of this repository, and as with the novel itself, for the most part I have not
read them in depth, but they are interesting to skim.

One active choice I made was to switch to "research" mode for the step "Research
and Worldbuilding", allowing Claude to delve into the Web for background on The
Cotswolds, 80s computing, libraries, whatever it chose.

Once the intermediate resources were produced, it turned out that churning out
the whole novel in one go was a bit much, so I gave it this rule:

```
When asked to write the first draft, work one iteration at a time.

Follow the plans in the project knowledge. This activity is phase 5 of the plan and encompasses steps 11, 12, 13 all at once.

In one iteration:

  - if the draft is complete, say "the draft is complete"
  - otherwise, choose whether to EITHER revise an existing chapter or create a new chapter
  - you may author the chapters in any order you like. 
  - create new chapters in artifacts called "CHAPTER n". Write a full chapter in an iteration.
  - revise each chapter a maximum of one time -- in the spirit of a human reviewing the previous day's work

At the end of the iteration, report the progress of the full book - chapters written, chapters reviewed, chapters not started.
```

Producing the draft was a matter of prompting "Start writing the first draft", 
then "next iteration please" each time it stopped. Of course this could have
been automated.

At no point did Claude use that opportunity to revise an existing chapter.

Following the plan created by Claude, a review was made of the draft, followed
by "line by line editing".

Where we reached in the plan, is getting feedback from test readers. I asked
Google Gemini to review the manuscript, in personas invented by Claude, 
answering questions created by Claude.

The reviews were pretty glowing. Gemini is evidently a people pleaser.

Claude then produced a 60 point plan towards a final version -- at which point I
decided enough was enough. So you have the beta draft.
