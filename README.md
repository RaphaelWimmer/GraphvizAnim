# GraphvizAnim

GraphvizAnim is a tool to create simple animated graph visualizations; it is
just a proof of concept, aimed mainly at teaching purposes. It is based on
[Graphviz](http://www.graphviz.org/) for the graph rendering part and on
[ImageMagick](http://www.imagemagick.org/) for the animated gif generation.

<p align="center">
<img src="examples/dfv.gif"/>
</p>

A *graph animation* is just a sequence of *steps*, a step is in turn one or
more *actions* such as: *add*, *hilight*, *label*, *unlabel* or *remove* a
*node*, and  *add*, *hilight*, or *remove* an *edge*. Animations can be built
by invoking suitable methods of a `gvanim.Animation` object (in a Python
program), or by parsing a simple text file (that, in turn, can be generated by
a program in any language).

The [examples](examples) folder contains few instances of such approaches.
After intsalling the package with `python setup.py install`, or using

	pip install https://github.com/mapio/GraphvizAnim/archive/0.2-alpha.zip

you can generate an animated depth first visit (in a 3-regular random graph of
6 nodes) by running

	python examples/dfv.py

or you can generate the simple animation described in
[simple.txt](examples/simple.txt) as

	python -m gvanim examples/simple.txt simple

You can generate an [Erdős–Rényi](https://en.wikipedia.org/wiki/Erd%C5%91s%E2%80%93R%C3%A9nyi_model) graph (with 10 nodes and edge probability
1/10) by running

	cd examples
	gcc -o er er.c
	./er | python -m gvanim er

Finally, you can obain an interactive visualization with
[Jupyter](http://jupyter.org/) by running

	cd examples
	jupyter notebook simple.ipynb

and running all the cells in order.

## Todo

Any help will be appreciated. Things to do to make this more usable are:

- [x] add `setup.py`,
- [ ] add tests,
- [x] add other *actions* (such as labeling of nodes and edges),
- [ ] document the Python code,
- [x] add option parsing to `__main__.py`,
- [ ] integrate this with [PyGraphviz](https://pygraphviz.github.io/),
- [x] integrate this with [Jupyter](http://jupyter.org/),
- [ ] add more relavant examples.
