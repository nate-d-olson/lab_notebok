Title:Setting up pelican lab notebook
Date: 2015-01-16
Modified: 2015-01-16
Category: Productivity
Tags: lab notebook
Slug: setting up pelican
Authors: Nate Olson
Summary: Setting up a static pelican website for use as a lab notebook. Able to include ipython notebook pages and markdown files.

# Setting up python virtual environment
	virtual env
	env/bin/pip install pelican markdown Fabric 
	git clone https://github.com/ipython/ipython.git
	cd ipython
	../env/bin/pip install -e ".[notebook]"

# Initializing website
	source env/bin/activate
	pelican-quickstart

# Pelican plugins
	* general plugins
		git clone https://github.com/getpelican/pelican-plugins.git
	* ipynb
		git clone https://github.com/danielfrg/pelican-ipynb.git
	* render math
		mkdir plugins
		cd plugins
		cp -r ../pelican-plugins/render_math .

# Modify Pelican
	* plugin information
		* pelicanconf.py
	* function for creating a template markdown file
	fabfile.py