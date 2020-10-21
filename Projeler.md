Proje Examples will be here in a just one repo!!!

==================================+


## HTML 
* [1.layout.html](https://github.com/anilodabas/project-examples/blob/master/HTML/1.Layout.html) Html temel düzeni ile ilgili çalışmalar.
* [2.Heading-paragraph.html](https://github.com/anilodabas/project-examples/blob/master/HTML/2.heading-paragraph.html) Başlık ve paragraf oluşturma ile ilgili çalışmalar.
* [3.Styling.html](https://github.com/anilodabas/project-examples/blob/master/HTML/3.styling.html) Yazı ve arka plan stilleme ile ilgili çalışmalar.
* [4.Formating.html](https://github.com/anilodabas/project-examples/blob/master/HTML/4.formating.html) Yazı veya görsel boyut çalışmaları.
* [5.Links.html](https://github.com/anilodabas/project-examples/blob/master/HTML/5.Links.html) Yazı üzerine link verme çalışmaları.
* [6.Images.html](https://github.com/anilodabas/project-examples/blob/master/HTML/6.images.html) Resim ekleme ve resim üzerine link verme çalışmaları.
* [7.Tables.html](https://github.com/anilodabas/project-examples/blob/master/HTML/7.tables.html) Tablo ve çerçeve olşturma çalışmaları.
* [8.lists.html](https://github.com/anilodabas/project-examples/blob/master/HTML/8.lists.html) liste sıralama ile ilgili çalışmalar.
* [9.Videos.html](https://github.com/anilodabas/project-examples/blob/master/HTML/9.videos.html) Video oluşturma ve boyutlandırma çalışmaları.
* [10.Audios.html](https://github.com/anilodabas/project-examples/blob/master/HTML/10.audios.html) Müzik(mp3) olarak oluşturma çalışmaları.
* [11.Block-İnline](https://github.com/anilodabas/project-examples/blob/master/HTML/11.block-inline.html) Blok ve inline kapsama çalışmaları.
* [12.Div-Span](https://github.com/anilodabas/project-examples/blob/master/HTML/12.div-span.html) blok ve kısım ayırma çalışmaları.
* [13.Id-Class.html](https://github.com/anilodabas/project-examples/blob/master/HTML/13.id-class.html) İsimlendirme ve sınıflandırma çalışmaları.
* [14.Booksmark.html](https://github.com/anilodabas/project-examples/blob/master/HTML/14.booksmark.html) Etiketlenen kısıma gitme çalışmaları.
* [15.Forms.html](https://github.com/anilodabas/project-examples/blob/master/HTML/15.forms.html) Form oluşturma çalışmaları.
* [16.Semantic.html](https://github.com/anilodabas/project-examples/blob/master/HTML/16.semantic.html) Semantic elementlerle sayfa oluşturma çalışmaları.

### CSS
* [Git: No Deep Sh*t](http://rogerdudler.github.io/git-guide/) A super simplified way of explaining git, basically a cheatsheet.
* [The Git Book](http://git-scm.com/book) Explains everything that's possible with git in lots and lots of detail.


The Git Flow
==================

The following snippet is designed to explain Vincent Driessen's [git branching model](http://nvie.com/posts/a-successful-git-branching-model/), at least as well as I understand it. Special thanks to [Stephen Koch](https://twitter.com/skoch) for being the true master here.

A way to think about Git and Github.
------------
Milestones of milestones of milestones. In other words:

- Open up a text editor.
- Type "Hello World".
- Save this file.
  - You have now created a "milestone" on your hard drive of this text.
	- You can now retreive that milestone by double clicking it to re-open it in your text editor.
	- This should be a concept you already understand quite well.
- Change the contents of that file again. Add in your own text. Save it again.
	- By saving it again you've overwritten the previous milestone.
	- You can certainly redo the work (e.g. replacing all the text with "Hello World" and saving again) but the original work is gone otherwise.
- Git saves milestones of milestones.

		git commit -am "By typing this command I am saving a collection of saved files."

- This is great because now we can roll back to old versions of files without having to retype. Aka "source control".
- However, wouldn't it be great if we could further save milestones in the cloud?
	- Aka milestones of milestones of milestones.
		- Github -> Git -> Save
- Github is two things:
	- git, in the cloud
	- a social network around source code
- All you need to do to push to Github:

		git push origin master

- Now one could "clone" that repository on another computer and not just get the latest code but the complete revision history on another computer.



Setting up
------------
Assuming your project is in a folder named "Project" on your Desktop.

### Starting from scratch
	cd ~/Desktop/Project
	git init
	git checkout -b develop
	touch README.md

- Open the README.md file you just created in your text editor. Describe your project. I've provided a basic template below for what it's worth. Save it.
- Go to Github (or Bitbucket or whereever you want to save your code in the cloud). Create a new project.
	- If you're on Github, ***do not check*** Initialize this project with a README since you just made one.
- Determine your SSH clone url. On Github it's probably something like ***git@github.com:USERNAME/PROJECT.git***. Should be on the project's page somewhere.
- Add your remote.
	
		git remote add origin {{the link you just copied}}

- Breaking that down
	- git :: The git command
	- remote add :: We're adding a remote connection for this repository
	- origin :: We're naming the remote "origin". You can also call this "github" or "bananasauraus" if you'd like.


### Cloning an existing repository.

- Determine your SSH clone url. On Github it's probably something like ***git@github.com:USERNAME/PROJECT.git***. Should be on the project's page somewhere.

		cd ~/Desktop
		git clone {{the link you just copied}} Project

- This creates a directory named "Project", clones the repository there and adds a remote named "origin" back to the source.

		cd Project
		git checkout develop

- If that last command fails

		git checkout -b develop

Updating/The Development Cycle
------------
You now have a git repository, likely with two branches: master and develop. Now bake these laws into your mind and process:

####You will never commit to ***master*** directly.
####You will never commit to ***develop*** directly.

Instead, you will create ***feature branches*** on your machine that exist for the purpose of solving singular issues. You will always base your features off the develop branch.

		git checkout develop
		git checkout -b my-feature-branch

This last command creates a new branch named "my-feature-branch" based off of develop. You can name that branch whatever you like. You should not have to push it to Github unless you intend to work on multiple machines on that feature.

Make changes.

	git add .
	git commit -am "I have made some changes."

This adds any new files to be tracked and makes a commit. Now let's add them to develop.

	git checkout develop
	git merge --no-ff my-feature-branch
	git push origin develop

Releasing
------------
Finished with your project?

- Create a feature branch as normal.
- Update the version history in the README.md file
- Update this to develop as normal.

		git checkout master
		git merge --no-ff develop
		git push origin master
		git tag v1.0.0
		git push origin v1.0.0

Replace 1.0.0 in the snippet here with your appropriate versions. Now you have a tag saved.