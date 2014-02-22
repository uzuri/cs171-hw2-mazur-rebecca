1. The following tasks are important: 
	* Adjacency: Which commit lead to which other commit (or came from the other commit).
	* Accessibilty: Which commit(s) lead to another commit; the path of commits taken to get to the current commit.
	* Attributes based on the nodes: who made this commit, what commit is it, where is the actual commit stored, what time was the commit made
	* Follow path: trace back a commit to the root and figure out who contributed.

2.  It becomes insanely tangled and cluttered, there's just not enough room for everything.  It also becomes essentially impossible to track changes due to the size of the graph (and I ran out of vertical space).  I had to jump to github's graph to really understand the graphs themselves; there are more contributors, of course, more branches, but also people tend to hold a branch for a while and then make a commit (assuming this is people taking specific bug/features and working them out before merging them back).

3. My graph is pretty spectacularly trashed by the larger repositories, even with doing some things to stretch things out and give stuff more space.

4. I think that I'd implement some filtering -- let people be able to drop some branches or narrow things down to certain stretch of time.  That'll let people focus in on what they're really working with at the moment.  I think I'd also try (if I could figure out how) to arrange for some sort of sorting that would allow for more active branches to be pushed closer to each other depending on the space in time you were looking at.  Mostly I'm thinking there needs to be ways to simplify for the user, since few people can handle that much content at once.  It might also be worthwhile to condence commits within a day into a single node and let the user drill down if they need more details.
