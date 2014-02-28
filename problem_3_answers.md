1. The following tasks are important: 
	* Adjacency: Which commit lead to which other commit (or came from the other commit).
	* Accessibilty: Which commit(s) lead to another commit; the path of commits taken to get to the current commit.
	* Attributes based on the nodes: who made this commit, what commit is it, where is the actual commit stored, what time was the commit made
	* Follow path: trace back a commit to the root and figure out who contributed.

2.  It becomes insanely tangled and cluttered, there's just not enough room for everything.  It also becomes essentially impossible to track changes due to the size of the graph (and I ran out of vertical space).  I had to jump to github's graph to really understand the graphs themselves; there are more contributors, of course, more branches, but also people tend to hold a branch for a while and then make a commit (assuming this is people taking specific bug/features and working them out before merging them back).

3. My graph is pretty spectacularly trashed by the larger repositories, even with doing some things to stretch things out and give stuff more space.  It still works, it just gets very hard to read, and very vertically deep (though in all fairness, lots of users kind of much up the usefulness of the github graph as well).

4. I think that I'd implement some filtering -- let people be able to drop some branches or narrow things down to certain stretch of time.  That'll let people focus in on what they're really working with at the moment.  I think I'd also try (if I could figure out how) to arrange for some sort of sorting that would allow for more active branches to be pushed closer to each other depending on the space in time you were looking at.  Mostly I'm thinking there needs to be ways to simplify for the user, since few people can handle that much content at once.  It might also be worthwhile to condence commits within a day into a single node and let the user drill down if they need more details.


Design Studio:


Analysis:

* These networks show commits, users, branches, commit ids, commit notes, and times of commits.  Other things you might want to show would be the commiter's username (so you can find him easily) and a direct link to the commit (so you can grab it easily).
* I don't see much use for git other than if you're a developer or someone who wants to download and use something stored on git (which probably means you're still a developer).  I suppose a user for the graphs themselves might be a project manager so that you can see how your team is doing (and who's doing the work).
* I actually think this graph does about all you could hope it would, but an interesting thing to show might be a slice of time kind of view, where you see commits over a selected period of time.
* This could be useful for a couple people: folks wanting to use a product (and looking for commits from a certain time period) and  managers (wanting to see exactly what was going on at a given time and who was doing it).  Let's take the manager; he'd probably most need the time and number of commits as applied to the person.  Dorect links to the commits would help him make sure that the commit was really a substantial one.


Sketch

The sketch for the design studio is hw2sketch.jpg

* I decided to use size for the primary visual variable (the number of commits over a time).  Color indicates which committer and matches the color of the lines in the graph.
* In this case clusters of commits are more important than individual ones, so they're grouped over time, and the overview graph doesn't even show the nodes.
* I'd rather summarize by true branches if it were up to me.  API design decisions makes that a royal pain to actually pull off.
* A node-link is a traditional way of showing git structures -- it is a tree, after all.  There really isn't a better way to show the data.


Explanation

My intention here was to give a "slice of time" view of the existing graph.

What you should get here is a mini-version of the existing graph (all lines) that you can select portions of to then be presented with a cut-away view of that time period showing which branches were active.

I thought this might be an interesting take on the graph; I know sometimes when working on a project you know when you last had it working and might like to go back then and try to snag the working content and see what might have flubbed up what you have currently live.  This gives you a quick way to get back to that slides of time and grab whatever changes might have been going on then.

This is a filtering method (though there are potentially others -- filter out users, filter out branches, filter out time periods completely).
