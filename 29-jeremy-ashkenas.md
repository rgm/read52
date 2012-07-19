# Can Code Be Like Literature?

Jeremy Ashkenas  
10 Apr 2011

https://docs.google.com/present/view?id=0AcVl9Wd2snSHYWpnY2RtcWRjZzlrXzMxZjRkZndoZzg&hl=en
http://dl.dropbox.com/u/5764687/jashkenas-code-as-literature.mp3

We don't just program because it's our day job; we write open source software because there's something deeply intellectually satisfying about code. And it has an interesting quality if you look at it.

So I want to step back and talk a bit about what makes code strange.

So, as a programmer, I think there's a lot we take for granted when we sit down in front of the machine and get to work. In this laptop right here, for example, there's like half a century of code history not only present but actually running.

And at the surface level you have programming language revolutions, and counter-revolutions and battles for web framework supremacy or build tool dominance. But at the base of code culture there's a deeper set of qualities that don't change that I think we do take for granted.

So, what I want to do this afternoon is review some of the things we take for granted about code, and take a moment to look at it with fresh eyes as kind of a cultural artifact, and hopefully this is all stuff you already know. But, it's about taking it from whatever place you know it deep down, and bringing it up to the surface, at least for half an hour.

So, we here at CodeConf are in a unique position. We take advantage of these crazy scripting languages--high-level languages--that are sort of minor miracles. And let's take Ruby as an example here. Not only that many of us belong to a community of Ruby programmers, but how crazy unlikely it is to have a community of Ruby programmers in the first place. You know, it's a strange idiosyncratic language which began with no corporate backing, little documentation in English, it's kind of against all the odds that it would make it big in the United States, and it's especially unlikely considering that programming languages in this country are often proposed, developed and promoted by large American companies.

And, by the end of this talk I'd like to have convinced you that we use languages like Ruby, Python and JavaScript because they allow us to write code in a way that resembles literature. But for now, let's say that we use high-level languages because somehow they fit the way you think. You know, they're fluent. And reading well-written code in a scripting language is an aesthetic experience. Because, let's be honest here, right: we certainly don't use Ruby for engineering reasons.

So this is the position I want to advance here. The fact that Ruby is as effective as it is is a strong argument against code as *just* applied mathematics or *just* applied engineering. It's an existence proof, because Ruby is many things but it's not the fastest language. It's not the most memory efficient, certainly. It doesn't have the best network libraries. It doesn't have the best features for concurrency. Doesn't run in a web browser. (Of course, there are people hard at work on changing all of those things).

But, despite all that it's an incredibly effective language to work in, as are all these sorts of languages. Now, we want to talk about why that's the case.

So, as a fair bit of warning up front, I'm going to rely perhaps more heavily than I should on Dijkstra and Knuth in this discussion. Here, looking dashing as always in their eye gear. And, as sort of the angel and the devil that sit on your shoulder while you sit down and wrestle with code, and I'll let you figure out for yourself which one is which.

So Dijkstra has many interesting things to say about programming, and I think that he's very good at explaining the reasons why code should be treated as a new phenomenon, and not like every other type of engineering. So, to put it quite bluntly, Dijkstra says, as long as there were no machines, programming was no problem at all. When we had a few weak computers, programming became a mild problem. And now that we have gigantic computers, programming has become an equally gigantic problem: "I do not know of any other technology covering a ratio of ten to the ten." And he often cites this sort of massive ratio of scale as a root of our problems.

Because as a programmer you're twiddling bits, you're poking Boolean true into Boolean false, you're working with bitwise operators. And at the same time you have to deal with streaming files on the gigabyte scale, or programming across, you know, hundreds, maybe thousands of networked physical machines. So, how can a computational technique that proves effective when you say have a puny couple thousand cycles per second at your disposal also work when you have a fleet of **GARBLED** servers, linked together in a **GARBLED** cloud. And, so, talking about this extreme range of sizes, of scale here at work, makes one think that code these days, as computers have grown, code must also be very large indeed.

And so, thinking about what it means to talk about the size of a code base brings us to our first important question but also a silly one. Right? If printing out the spec for your code stacks up yay high on the table, describing exactly what it does in precise language, how big is your code then? If your company has invested 100 man-years into the code base, how big is your code then? How big can it possibly be if when it's actually running, it exists in, you know, invisible electronic patterns in circuitry only nanometres wide? Is it ephemeral like a song, does it sort of disappear after it runs? If you write a piece of code that never runs, is it still software, or have you written a bizarre poem?

So, Dijkstra continues:

> "By evoking the need for deep conceptual hierarchies, the automatic computer confronts us with a radically new intellectual challenge that has no precedent in our history."

And this is nice and bombastic: Dijkstra at his best here. So, talking about how the incredible scale at which code operates requires you to structure your code into deep hierarchies, to effectively talk about all the different levels of data, basically, as they're flowing through your algorithms.

And so this is Code as a Fundamentally New Thing. And Dijkstra continues. He says:

"Coping with radical novelty requires an orthogonal method. One must consider one's own past, the experiences collected, and the habits formed in it as an unfortunate accident of history, and one has to approach the radical novelty with a blank mind, consciously refusing to try to link it with what is already familiar, because the familiar is hopelessly inadequate. [...] Coming to grips with a radical novelty amounts to creating and learning a new foreign language that can not be translated into one's mother tongue."

So here we get Dijkstra the Zen Master, saying that in order to understand your code, first you must empty your mind and forget everything that you know. Well, I don't know how ** something ** this really is, because we tend to deal with our code and software in general in terms of metaphors and things that we're familiar with.

But, let's assume that he knows what he's talking about for a moment, and sort of approach code from first principles as if we had no idea what it was all about.

So start with the most obvious and sort of literal-minded aspect of code and get into the physical side of it before going out into the fluffier stuff.

Right, here's the elephant in the room, what you need to say about code first up, of course, is that it's all just made out of ones and zeroes. Here we have the word "code" being unpacked as binary.

And, of course, right, ?? proportionally ?? this doesn't need to be terribly depressing or even limiting because at this point in our culture almost everything else is also just ones and zeroes. Right? Fine art, films, music, books, news, politics: a large part of human cultural production is already mediated through digital bits. So this doesn't have to be a something to terribly concern us, that code just exists in digital bits.

So this is something that we know but, again, something that we take for granted. Right? We lucky to be able to say oh, it's a string, I know what a string is, and not think about the fact that everything that the string consists of is a layer of crazy hacks, you know, stacked on top of one another, right? Chicken scratch on magnetic disks getting treated as small numbers, and then the numbers being codified through a fancy hierarchy to become you know symbols for the English language.

So code is logic.

Here's Knuth's definition for what code is, what an algorithm is.

It has to be finite. Infinite loops are not algorithms, right? They're not code. It has to finish.

Each step must be unambiguous. It must be definite.

For input, there must be zero or more inputs. For output, there must be one or more outputs. If an algorithm doesn't produce anything, is it really running? And you can think about this. If you write a really, really pure Haskell program, and you don't do any I/O, did your program really run, or did ?? GARBLED ??

And finally, it has to be effective. And what effectiveness means is you need to be able to do it on paper by hand. There's no magic involved here in the algorithm, right? It's something that maybe if you had many lifetimes to work it out you could work it out with pencil and paper.

So, what's going on at the logic level? And, it's good that we've heard so much today about code as it exists in dialog with documentation, and as it exists... the difference between the mental model of your code right ?? GARBLED ?? and the actual code as it's running.

So we have say, let's talk again with Ruby as the example here. Fundamentally twiddling little bits of logic down at the circuit level but you start out with the text that's writing that you write. The Ruby parser is going to build that into an AST. In Ruby 1.9 the AST is going to tran?? to byte code. The byte code is going to be interpreted by the Ruby VM and become machine instructions. And then with every cycle of the CPU a little piece of one of those instructions is executed. Not even the entire thing necessarily. It often takes more than one cycle to run a given instruction. For example, on a 286 it took 20 cycles to do multiplication, and then later on, on a Pentium it only took one.

So there's a big semantic gap here, between what's going on at the logic gate level and what's going on in your code and in your head. And the two are the same, literally the same, you can transform one into the other, but looking at them you wouldn't know it.

This is different than other systems of symbolic representation. If you take the map of downtown San Francisco we were talking about yesterday, looking at the map and looking at the real city, you'd be able to recognize that the lines are streets, the blue bits on the edge are San Francisco Bay... But I dare you to imagine that you could possibly recognize what's going on if you were to observe the electrical signals racing around the CPU when you write `!value` in Ruby. Even for things that could be one to one. For example, if you say that "not" could just be one logic gate. But, I'm not sure exactly what happens when you write that in a high-level language but you're pretty damned certain it's not just doing that; it's doing a hell of a lot more. ??? something ??? find out what.

So the next aspect I want to talk about is Code as Law.

So here we've got a little bit of code. Ball's X coordinate is getting modulo equal to the width of the screen; ball's Y coordinate is getting modulo equal to the screen's height. What does this mean? It means that as the ball moves around it can't leave the screen. It's constrained to the surface. It'll go off on one side and come back on the other. And so this is code as it sort of describes a possible space of the bits. And what is allowed, and what is not, and what is not permitted. Because we know a blank computer screen can display any film ever recorded, any photograph, any work of art. A blank hard drive can contain any book. A blank CPU being Turing-complete can run any computable program. And so programming is also sort of the process of restricting this explosion of possibilities and structuring them into something meaningful.

You start when you begin with a state of absolute entropy. A blank hard disk is kind of like the heat death of the universe. Every bit identical, zeroed out in all directions. 

And then code happens.

And your program is acting like the laws of physics, shaping the possible bits that are allowed to exist and constraining them to certain patterns. But it's not like the laws that we're familiar with, because in the machine code is the only *possible* law. There's nothing else outside of it. So in the real world we understand how laws control our actions, but in the machine all code behaves as law. So this metaphor starts to make less sense because if running code is the only action that takes place, there's nothing there to regulate outside of the code. So, if the ball would never want to move off the screen, then does it mean to say that it's being constrained? It might not mean anything.

But code as law becomes much clearer when a human begins to be involved. I'm not just talking about authentication and authorization, sanitization, permissions, ACLs, all that kind of stuff. But when someone runs your code, you have a person trying to express themselves ** SOMETHING ** through your software and your software is the thing constraining what they're allowed to say and what not to say. And so because complete control is the default state of software, designing for freedom of expression in your code becomes kind of a moral value. And as programmers we need to be cognizant and vigilant of that responsibility.

Because programming is software just like everything else, you can take a minute to think of programming languages in this way. Think of the ones that you've used that constrain your programs into a mathematically sound structure, versus the ones that let you scribble and draft and sludge any sort of idea that comes into your head. ** SOMETHING ** come back up later.

So after Code as Law, let's talk a bit about Code as Art. Because in terms of "The Law" in the United States, code has a legal status similar to that of art. Music, fine art, design, writing and code are all works of the mind for which private property rights are recognized.

So here we've got our friend Knuth--who is the Outer Paren in this picture--and he's one of our main champions of Code as Art. And not only because his magnum opus is titled "The Art of Computer Programming," but because he really believes that Art-with-a-Capital-A is the correct category for what we do when we write code. In fact, when he won his Turing Award for Lifetime Achievement, his Turing lecture was titled "Computer Programming as an Art," and the entire thesis of that lecture was that programming is more properly called an art than a science. Which is, you know, a big thing for someone you'd say who has done more to advance code as a science than I think anyone else has.

What he has to say about it, right:

> "Science is knowledge which we understand so well that we can teach it to a computer; and if we don't understand something, it is an art to deal with it."

And this is a cute little proof, right, because we all know that computers can be taught to program, yet programming remains an art. So let's see, now that we have Knuth's position, if we can situate where code might fit among other arts. One way that we can start to find out where programming sits in relation to the arts is to see how they've changed over the course of the last century. There was a time when art used to be unique. One artist would work on a particular piece, and it couldn't be **CAPTURE?** reproduced. But, for the last hundred years, we've lived in a world where symphonies can be enjoyed in a living room, movies premiere on thousands of screens worldwide simultaneously, and a painting is more often seen on a printed page or a poster or a screen, than it is on a wall. So, Walter Benjamin, who wrote about this problem originally, has to say:

> "Even the most perfect reproduction of a work of art is lacking in one element: its presence in time and space, its unique existence at the place where it happens to be." 

So this is the aura of the original. This is the thing that's changed in terms of reproducing art, and having it be distributed. Unlike this kind of art, that needs to have, like a sculpture, like a painting, that has an original, if you copy it you don't have the same thing. Code has no original. There's nothing there to carefully imitate, there's nothing there to faithfully transcribe, and this isn't to say that you never copy a piece of code, but the extent to which you copy an existing piece of code, your copy is only interesting in the ways in which it differs from the original and not the ways in which it ** SOMETHING ** the same. I'm not going to get any credit for doing `cp` on a program and having it work exactly the same. Only if I modify it does it become interesting.

Here we can draw a line between the concrete arts and the abstract arts. Where the concrete arts like say musical performance, a painting, or a sculpture or a play, you have an art object or an event, embodied in a single space or time. You can record it, you can photograph it, you can copy it, but you no longer have the original. And these are unlike code, which would be considered an abstract art, like the others, like architecture, musical composition, writing, where with the abstract arts you lose nothing from making a copy, from reproducing a blueprint, reproducing a score or a book, and they need to be reified, they need to be performed, they need to be executed in order to become real. So in the same sense that we asked earlier what is a piece of code that never runs, we can also ask, what is a blueprint for a house that is never built, what is a song that has never been played, and what is a book that has never been read?

So, probably the closest cousin among the abstract arts to code is writing, because they're both forms of written expression, you're expressing yourself through text. But Code has this sort of funny property that makes it unlike other types of writing. Code has a dual audience. With most works of art you have a single audience. You're performing for the audience ** SOMETHING **. You're painting for the viewer. You're writing for the reader. But with code you have two audiences: you write it for the machine to understand and you write it for the reader to understand. And this is sort of a simple point but it has a profound root at the base of the way that we write software. If we were only writing for the machine, and I think a lot of the time we forget that we're writing for the reader too, and we pretend like we're only writing for the machine because we understand the problem space, or understand the engineering, if we were only writing for the machine we never would have stopped writing in machine code, right? Because we would still speak to the processor in the way that the processor is best equipped to understand. But the entire history of programming languages is a history of trying to find the optimal position for the hardware of the time, where you can address both audiences at once, where you can speak clearly to the machine as well as the reader and we're shifting ever more towards the reader as we go along, because the fundamental point is that the machine doesn't care, right. In the end the machine doesn't care at all. Doesn't care if you feed it from instructions carefully poked into main memory with tweezers, or if you generate code that generates code that generates code. The computer isn't going to pat you on the back just because you performed some little optimization that has no overall effect on the runtime, it just doesn't care.

But at the same time the machine has the final word here. If the machine doesn't understand what you've written for it then your code is broken in a very literal sense. Hopefully a syntax error but not always. The machine is the final arbiter of what broken code is.

What does this mean for you as a reader, that the machine is the final arbiter of working code? It means that you can't just read it as you would read English. As you read code you have to constantly be keeping off little bits of it running in your head and executing it. Sort of monolithic. Whether or not someone stuck ** SOMETHING EACH LOOP **, you still have to pretend like you know what each does. So this creates an aesthetic effect when you read a well-written program. Because by reading it you're also sort of running it, and you learn how to perform the task that the program performs. So in a literal sense it shows you how to accomplish the task instead of telling you how to it, and this is part of the enjoyable feeling of reading a program that you don't understand. Because it's much more pedagogically complete than an explanation might be.

And once again, there's a parallel here to literature. When Montaigne originally invented the essay as a form the point wasn't to write down something that you knew about, the point was to through the process of writing come to understand something new. I think that as programmers we're familiar with this feeling. Starting in on a project where you don't necessarily know how the implementation's going to shake out, when you begin, we can relate to the experience of working through a thorny problem by writing it out, by running it, by debugging it, by testing it, by rewriting the broken bits until you sort of understand how the pieces fit together.

So, this need to read and execute large programs makes them very much less manageable than they otherwise would be, because you can't just read them. You also have to keep them in your head. So Dijkstra says, the competent programmer is fully aware of the strictly limited size of his own skull, therefore he approaches the programming task in full humility.

Because just reading through it doesn't give you much ** power to reason about it, and because you're constantly executing it in your head, we quickly run out of mental space for doing this, and you have to limit yourself to small pieces of the program and hope that other people who are the owners of the mental model of the other domains of the code and Dijkstra has a thought for us about we might solve this problem of having to keep the code in your head as you work with it. He says:

> "It has been suggested that there is some law of nature telling us that the amount of intellectual effort needed grows with the square of the program length. Thank goodness no one has been able to prove this law. And this is because it need not be true. We all know that the only mental tool by means of which a very finite piece of reasoning can cover a myriad of cases is called 'abstraction;' as a result the effective exploitation of his powers of abstraction must be regarded as the one of the most vital activities of the competent programmer. In this connection, it might be worth-while to point out that the purpose of abstracting is not to be vague, but to create a new semantic level in which one can be absolutely precise [...] I now suggest that we confine ourselves to design and implementation of intellectually manageable programs."

And so this is Dijkstra talking about this problem, of seventies-sized code problems, and the problem of fitting it in your head. But this is still a problem we have today; we haven't solved it yet. Here's a more modern author, Steve Yegge:

> "I happen to hold a hard-won minority opinion about code bases. In particular I believe-- quite staunchly, I might add--that the worst thing that can happen to a code base is size."

And so Steve Yegge has been in the position to have dealt with several code bases of quite a large size. So, the history of programming languages addresses this right, we're trying to figure out how we can address both audiences correctly, as the machine gets faster and faster we can begin to speak more clearly to the reader and make it easier for them to keep everything in their head, and rely on the machine to do a little bit of extra legwork to understand us. And the point that I'm trying to make here is that as high-level language programmers in particular, as people who use Ruby and python and JavaScript we take this argument to the extreme every day. And I think we need to be aware of that, that you're taking a stance just by using those languages.

So we know this quite familiarly from programming languages where you have two different ways to transform a list of strings into all caps through a function and then print it, but this plays out in natural languages as well, we've all heard about Eskimoes having fifty different words for snow, which by the way isn't true, but there are better documented cases of Amazonian tribes deep in the rain forest that have no way of counting, that can only say many or few, or groups of islanders that don't have words for cardinal directions. You can left, you can go right, but you can't go north, south, east, or west. Or, languages without tenses, and no way to distinguish between past and future events in words. So, Dijkstra takes one side of the argument, what should be allowed to be said in code. And this is kind of a fun one. He's talking about how to deal with an introductory programming seminar. He says:

> "We stress that the programmer's task is not just to write down the program, but that his main task is to give a formal proof that the program that he proposes meets the equally formal functional specification. While designing proofs and programs hand in hand, the student gets ample opportunity to perfect his manipulative agility the predicate calculus. Finally, in order to drive home the message that this introductory programming course is primarily a course in formal mathematics, we see to it that the programming language in question has not been implemented on campus so that students are protected from the temptation to test their programs."

Oh, the outrage, that you might be tempted to ever test or run your program. Because of course testing is a terribly fuzzy and error-prone way to ensure the correctness of your program. What you really need is a proof, right. And so He goes on:

> "Another lesson we should have learned from the recent past is that the development of 'richer' or 'more powerful' programming languages was a mistake in the sense that these baroque monstrosities, these conglomerations of idiosyncrasies, are really unmanageable, both mechanically and mentally."

So that's the Dijkstra side. And here we have an opinion-maker who could hardly be more opposite. This is Matz talking about programming language philosophy saying--Matz being the creator of Ruby--saying that

> "Sometimes people jot down pseudocode on paper. If that pseudocode runs directly on their computers, it's best, isn't it? Ruby tries to be like that, like pseudocode that runs."

And here's the point where our ((something)) argument isn't just theoretical, right? Dijkstra's famous "GOTO Statement Considered Harmful" essay marked the moment at which structured programming ((was born)), and to treat it quickly apart from just abolishing the use of GOTOs, structured programming aimed to make programs more understandable in a mechanical sense by limiting them to three methods of combining computation: you could do sequencing, selection or repetition. Statements in order, if-elses to choose which branch to run, and repetition loops to do things repeatedly. This is kind of the manifesto for procedural programming right.

But who do you imagine might be the main person to rebut Dijkstra's original paper on "GOTO Considered Harmful?"

Why, Knuth, of course. He responded with a paper called "Structured Programming with GOTO statements" in which he demonstrated with examples that sometimes the GOTO can be used to make the code both more efficient and clearer. Damn the engineering, clarity is what we're going for here.

So, later on then Knuth actually introduced Literate Programming as an alternative to the structured programming paradigm. And so, what Knuth has to say about the fundamental idea of literate programming is: "Let us change our traditional attitude towards the construction of programs. Instead of imagining that our main task is to instruct the computer what to do, let us concentrate rather on explaining to human beings what we want the computer to do." Address the reader instead of the machine. "The Practitioner of literate programming is to be regarded as an essayist, whose main concern is with exposition and excellence of style."

So suddenly, instead of designing a well-structured, well-ordered mechanical computation, you're sort of writing an explanatory essay, and the code is filling in the details in the prose. And this would be a good point to mention that if you're interested in writing this sort of code as an essay, you should talk to Peter Seibel--((yesterday))--about Code Quarterly, because that's kind of the idea behind the code reads that they want to work into that magazine.

So here's a rendition of Knuth's literate programming this is the classic adventure game "Adventure," which has spawned the genre, in FORTRAN, as sort of an essay that explains how the program works, from 1976. And here's a literate program from last week. This is the annotated source code to Pow, which is 37Signals's new development server for Rack apps.

This is bringing us to Code As Literature.

And, you might be thinking I'm talking about literature like fancy fiction. That's not really what I mean. So let's dive in to what we mean when we talk about literature here. We can consider a book or an essay kind of like a program that runs in the mind of the reader, right? When we write literature, we do so to convey certain definite meanings to the minds of the readers and the minds of the audience, and a great author is great because they're able to craft language that evokes the same intended meaning with force and subtlety and precision across a large swath of the reading public. So, what we mean by this is that meaning belongs to a text or to a program to the extent that it acts upon intelligence in a particular way. Imagine trying to write a piece of software that accomplished something in a world where every place it ever ran was a different platform. Machines read the same text in the same way, but each human reader brings their own histories, assumptions and prejudices to a text when they read it. And so if a text provokes wildly different unrelated thoughts in its readers, than to what extent can it be said to have meaning in it? It doesn't have any right? Meaning belongs to a text to the extent to which it acts on ((intelligence)) in a particular way. And unlike literature of course code has this nasty property where even the slightest perturbation has terrible consequences. Flipping a bit or forgetting to put in a semicolon will break your program, where to misspell a word in an essay, there's no such similar problem to the meaning of the text.

So we can say that a textual work is literary if it contains a high density of meaning. And we're contrasting this from in part where you have a high density of emotion in the work. And making this sort of dividing line between finding abstractions to compress meaning into small amounts of text versus having artistic works where there's a high density of emotion in it is something that artistic theorists already do. So Susan Sontag in her book "Against Interpretation":

> "In a culture whose already classical dilemma is the hypertrophy of the intellect at the expense of energy and sensual capability, interpretation is the revenge of the intellect upon art."

This book is a manifesto, saying: “Get your content out of my Art. Art should have no meaning, you shouldn't be able to talk about what it's about, Art should be a purely emotional sensual experience.”

And you know, fine by me. We'll talk about how you can do the meaning side of it and leave the emotion side to the artists. And we all know this from the spectrum of art forms that we have. You can talk about a painting like a Rothko painting, and I dare you to tell me what that painting is about, or what its content is, but you might have a strong emotional reaction to it, or you can have things that are both highly artistic and highly literary, like say the Sopranos, where you have very emotional plot twists but you also have plot, you have characters and a high density of meaning in there also and then you have books of essays, where maybe you'll feel something maybe you won't, but you're going to learn a hell of a lot and have a very strong high count of meaning per word there.

So, this comes back to code in terms of sort of the fundamental ideas behind some programming paradigms, like Alan Kay and object-oriented programming, right:

> "While we count the lines of code we use (which are expressed in languages with careful syntax we define), the battles here are fought, won or lost on how much power of meaning lies under the syntactic forms."

When you're designing a programming language or designing a programming paradigm to fit as much meaning into the code as possible. Writing practice in general, both in books and in code, is marked by the huge expressive powers that abstraction can give to the written word. You can have a single word that stands for a complicated concept, or equivalently thousands of machine instructions and clock cycles. And that's just one word. Paragraphs or methods, function bodies, can provide a large explosion in possibilities of meaning that might take shape in the reader's mind or might take shape, might be enacted ((GARBLED)). So to write literature and to write programs you have to decide how to balance the expressiveness of your language versus your control over the details. Because a literary abstraction can be seen as a way to trade precise control over how it's going to be accomplished for strong expressive power.

So you can choose to twiddle bits and place your opcodes or you can say `list.eachNewItem()` and not caring about what the class or type of the item is. And let's be clear here, right: because when we sit down to write code it's not an inevitable thing. We're still *writing*.

Almost every other field of engineering has been transformed by computer-aided design. If you're an architect, or industrial engineer, or an engineer of any stripe you probably have some kind of CAD software to create your systems. And, if any field of engineering should have been transformed by computer-aided design first, it should have been software.

But that hasn't been the case. And every graphical, visual, structured, database-driven programming language has failed, and we're still using plain text. We're still using plain writing to get our ideas across.

I don't think this is just an unfortunate accident of history, that we're not coding by drawing lines between 3d software objects on a screen. I think it tells you something about the expressive power of the written word.

We're familiar with a standard set of code abstractions, because when you're building on top of little streams of numbers almost everything has to be an abstraction of some kind: strings, fixnums, functions, classes, models, proxies, factories, all those kinds of code abstractions you're used to.

It turns out that literary forms and literary abstractions aren't necessarily so different or so alien. So let's go through a few of the fun ones.

*Metaphor*: Circle is an Ellipse. Except that it's not quite the same thing, it's specialized in a certain way.

*Simile*: where we say a rose is like many other things that are also fragrant.

*Synecdoche*: where you have a piece of the thing standing for the entire thing itself. So if we're talking about a tree, we can refer to the root node and say that the root node is the tree, because it's a recursive data structure and any sub-tree can used as the entire tree. And also in C, where a pointer to the beginning of the array can be treated as a reference to the entire array itself.

*Metonymy*: where instead of a piece of the thing representing the thing, you have an attribute of the thing representing the thing. So here we have in a database say, the ID of the document can be used as a handle to the document and it represents it.

*Personification*: this software knows how to clear its cache.

This is something we fall into all too often for Dijkstra. We can imagine what Dijkstra has to say about personification. He says:

> "It is to fight the 'if-this-guy-wants-to-talk-to-that-guy' syndrome: never refer to parts of programs or pieces of equipment in an anthropomorphic terminology, nor allow your students to do so. [...] I have now encountered programs wanting things, knowing things, expecting things, believing things, etc., and each time that gave rise to avoidable confusions. The analogy that underlies this personification is so shallow that it is not only misleading but also paralyzing."

And this is extra-funny in this day and age, in contrast with the great winner of the programming paradigms in recent history. Object-orientation is explicitly a biological metaphor. Alan Kay's design for object-oriented design was inspired by biological cells: where you have independent, self-directed, encapsulated units with specific capabilities and qualities of their own. He figured that it would be easier to reason about a group of miniature programs that could be treated as individual entities in their own right than it is to reason about a single, all-encompassing, overarching master program.

***

To wrap things up, as a final exhortation:

Contributing to open-source software is the programming equivalent to being an engaged citizen in your community. It's the way that we participate in a world of code as literature, reading what others have written and writing for others to read our code. So it's not only about getting bug reports and patches and pulls on Github, it's about reading and writing code, being edited by your peers and editing others, and learning how to express yourself in code in a way that's understood clearly by your readers, and not just having a private conversation with the machine.

I'll leave you with this from Knuth:

> "Some programs are elegant, some are exquisite, some are sparkling. My claim is that it is possible to write grand programs, noble programs, truly magnificent ones!"

Hopefully I've been able to demonstrate that while Dijkstra has an excellent sense of what the fundamental problems with code are, Knuth has a much better handle on how we as writers can solve them.

Thank you.


