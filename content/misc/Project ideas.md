- [ ] Write a TUI app that does basically `git log --oneline --graph --all` in rust to learn more about how to do TUI stuff in rust. (ratatui, libgit2)
	- Basically implement some small subset of features from lazygit for learning purposes.

- [ ] Have another go at writing a raytracer in a weekend but now in rust instead of cpp.
	- The book uses a bunch of modern cpp features, like smart pointers.
	- The aim of this exploration would be to see how you could write the same code in rust without those kind of language features.

- [x] Write an interpreter in rust.
	- Progress: https://github.com/leonardo-toffalini/lexer-rs
	- [x] lexer
	- [x] parser
	- [x] evaluator

- [ ] Do more adhd trap zero player games in lua with love2d.
	- [ ] Closed battle arena with rotating circle with different weapons attached.

- [ ] Extend the simple qr code generator to track how many times the code has been scanned.
	- Basically do a tinyurl type of redirect service.
	- Generate a qr code that leads to the site first, then redirects to the actual destination while tracking traffic.

- [ ] Write a simple but fun platformer game.
	- Previous attempt: https://github.com/leonardo-toffalini/platformer

- [ ] write a gps tool which can show you GPX data offline, im not paying 10$ a month for an app that loads a file

- [ ] 3d rubiks cube game, could lead to some group theory explorations when trying to write a solver

- [ ] learn more about shaders by reading through the book of shaders: https://thebookofshaders.com/

- [ ] learn even more about shaders by rewriting some old projects that would greatly benefit from having work be done on the gpu instead of the cpu:
	- [ ] raytracer in a weekend, the book does all the work sequentially for each pixel on a single thread of a cpu
	- [ ] rewrite the fluid sim (Stam fluids article) with gpu support

- [ ] game of life in latex, because you can

- [ ] learn typst

- [ ] look into nix-darwin, git it an honest shot if it sounds interesting

- [ ] look into the llvm kaleidoscope tutorial: https://llvm.org/docs/tutorial/

- [ ] play around with voronoi algorithms, and Delaunay triangulation
	- [ ] implement different algos for voronoi
	- [ ] implement different algos for Delaunay triangulation
	- [ ] take the graph dual of one to get the other
	- [ ] make a mesh from a point cloud using Delaunay triangulation
	- [ ] make a moving cell like animation with voronoi diagrams
- [ ] do something similar to this: https://www.youtube.com/watch?v=YGLNyHd2w10
