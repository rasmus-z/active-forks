# active-forks

> Find the active github forks of a project

This project allows you to find the most active forks of a repository.

It is based on [techgaun/active-forks](https://github.com/techgaun/active-forks), but with some added features which I found useful when comparing forks:
* include the **original repository** in the list, marked in bold
* retrieve **commits of each fork** and show the differences
* click on box in the **Diff** column to see the commits
* works after providing a **personal GitHub token**. It is used only to increase the limits to query to API.
* after expanding **Options**, it is possible to increase the **maximum amount of forks** to retrieve and to utilize some kind of caching

## Optimizations

Because this version retrieves commits from every fork which is slow and uses your quota (it resets every hour, don't worry), I added two options for caching results:
* **Same Size** - if a fork has the same size as a fork that has already been read, it is assumed to be the same and contain the same commits.
* **Same Push Date** - same but looks at the Last Push date.
If both are selected, both conditions have to be satisfied at the same time.
If the condition is satisfied, commits for the second fork are not retrieved but assumed to be the same as in the first fork.
