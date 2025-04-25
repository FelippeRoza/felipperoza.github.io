---
layout: post
title: Artificial Artist - Can Artificial Intelligence create art?
---

Art is a utterly important tool that allow human beings to express emotions and ideas created in our imagination. It plays a fundamental role in a social context that can also be entertaining and bring insight and understanding.

The desire to develop computational methods with artistic capabilities is not something recent. Ada Byron expressed her dream to develop a computer able to create music more then 150 years ago [1].

The big question is: Can something created by a machine be considered art?

## What is art?

Defining art is not an easy task due to its inherent subjectiveness. According to the Oxford dictionary, art is defined as:

“The expression or application of human creative skill and imagination, typically in a visual form such as painting or sculpture, producing works to be appreciated primarily for their beauty or emotional power.”

There is a branch in philosophy that deals with the concept of art and beauty, called aesthetics. The following definition of aesthetics is found in the Oxford dictionary:

“ A set of principles concerned with the nature and appreciation of beauty. The branch of philosophy which deals with questions of beauty and artistic taste.” 

In aesthetics, a viewpoint is responsible to define how some object will be classified as a piece of art or not, depending on several factors such as personal taste, cultural background, art form, etc, as pointed out in [2]:

“An aesthetic viewpoint determines how an object is understood as a work of art and how the quality of an object is judged when it is understood in this way. A viewpoint may be thought of as a construct of an observer used to consider objects as works of art and as a construct of an artist used to produce new works. 
There are many possible aesthetic viewpoints. They vary for different people, different cultures and different art forms. The variety of viewpoints is apparent when two different people understand and appreciate the same object as a work of art in two different ways or when two different artists produce two different objects both of which are claimed to be good works of art.“

With these definitions, it becomes clear that artificially developing (or learning) an aesthetic viewpoint should be the basis of an artificial artist.

## Can Ai create art?

The short answer is: yes, why not? As stated before, if we have a good definition of an aesthetic viewpoint, it is possible to develop an algorithm able to evaluate art.

The main problem is the lack of knowledge about the rules that drive artistic creation/evaluation in human beings. That makes it really difficult to elaborate a closed algorithm able to produce artistic pieces. The best approach may be using metaheuristic algorithms that search in a big set of possible solutions in order to develop its own sense of aesthetics.

In [3], Penousal Machato et al. present 5 features that an Artificial Intelligence must possess in order to become an artist:

1. Learning: The system must be able to improve its skills and adapt its art expressiveness according to new stimuli, like human artists do.
2. Own aesthetics criteria: Being able to evaluate its own artistic creation and from other artists is essential for any art creator. Even not existing a universal criteria for judging art, each individual has to develop its own standard, based on its personality.
3. Creativity: Creating novel and innovative pieces of art is what define an outstanding artist. The system should not apply small changes to existing artworks, but rather create something completely new (it may be influenced by other artist works, though).
4. Equality: The system should not be subject to the human will; it should interact with human or artificial agents at an equal level.
5. Sociability: Art cannot be created without social context. The artificial intelligence must be able to access artistic production as a source of inspiration.

In this same paper, a two module approach is proposed. The first module is an evolutionary engine, based on Genetic Programming, responsible to create new artworks. The second one is an adaptive classifier that was able to “to capture relevant stylistic properties” and “discriminate successfully between authors and styles”. However, even with good results, this system fulfills only partially the aforementioned requirements. 

I will present some other publications with artificial systems that are developed to create art, even though, to the best of my knowledge, there is any artistic system which fulfills all requirements.

### Music analysis and composition

In [4], the authors present an Artificial Network trained by using the popularity of 992 musical pieces as an aesthetic criterium. This system autonomously created variations of J.S. Bach’s Invention #13 in A minor (BWV 784) that were found to be aesthetically pleasing to many listeners. The prominent issue claimed in this paper is the difficulty to find truly bad music (here defined as unpopular ones), since most bad examples of classical music were not archived.

### The Robotic Action Painter [5]

Leonel Moura developed a robot that creates novel paintings.
The RAP [Robotic Action Painter] achieves artificial creativity by means of randomness, stigmergy and chromotaxis. This robot is additionally able to determine, by its own means, the moment in which the painting is finished.

### DeepArtificialComposer [6]

In this work, a recurrent neural network model of note transitions for the automated composition of melodies, called Deep Artificial Composer (DAC), is presented. DAC is able to generate melodies consistent to the style of the training examples (e.g. Irish and Klezmer music). 

## Conclusion

Creating and enjoying art is one of the particular things that differentiate human beings from other creatures. A system able to develop artistic sense would represent a big step into more complex artificial intelligences and to give a better understanding about the human brain operation. 

Even if the available artificial artists don’t fulfill a rigid set of rules to be considered real artists, we have examples of systems able to create outstanding material. This ability, in my perspective, makes the machines more human.


[1] MOORE, Doris L. “Ada, Countess of Lovelace: Byron's legitimate daughter.” HarperCollins Publishers, 1977.

[2] Gips, James, and George Stiny. "An investigation of algorithmic aesthetics." Leonardo 8.3 (1975): 213-220.

[3] Machado, Penousal, et al. "On the development of evolutionary artificial artists." Computers & Graphics 31.6 (2007): 818-826.

[4] Manaris, Bill, et al. "A corpus-based hybrid approach to music analysis and composition." Proceedings of the National Conference on Artificial Intelligence. Vol. 22. No. 1. Menlo Park, CA; Cambridge, MA; London; AAAI Press; MIT Press; 1999, 2007.

[5] Moura, Leonel. "A new kind of art: The robotic action painter." X Generative Art Conferece, Politecnico di Milano University (2007).

[6] Colombo, Florian, Alexander Seeholzer, and Wulfram Gerstner. "Deep artificial composer: A creative neural network model for automated melody generation." International Conference on Evolutionary and Biologically Inspired Music and Art. Springer, Cham, 2017.
