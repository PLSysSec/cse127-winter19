serve:
	mkdocs serve
build:
	mkdocs build
publish: build
	-git add site && git commit -a -m "update site for publish"
	cd ..  && git subtree split --prefix cse127-fall19/site -b site 
	git push -f origin site:site
	git branch -D site
	ssh login.eng.ucsd.edu 'cd /cse/htdocs/classes/fa19/cse127-ab/ && git fetch && git reset --hard origin/site'
	#ssh dstefan@login.eng.ucsd.edu 'cd public_html/cse127-fall19/ && git fetch && git reset --hard origin/site'
remove:
	git push origin :site
install:
	sudo pip install mkdocs
	sudo pip install mkdocs-material
	sudo pip install mkdocs-include
