This is my personal docbook project which helps me write a lot of blogs and articles.
I had an Ant-based alike project before which helped me complete my first book - ["UnveilSpring"(Spring揭秘 In Chinese)](http://product.china-pub.com/195969), but it just works. After I moved to Maven, I found the docbkx maven plugin, so it finally helped me build this archetype project.

To start to use it, you need to know some common locations:
### 1- src/main/docbook  
you put your docbook writings under this directory, sub-directories are allowed. In practice, you should create its own sub-directory for your articles, the reason is with each of your article, it not only contains words but also pictures and other media materials. So usually, before starting to write a new article, you create a sub-folder under src/main/docbook and  at least create an "images" sub-folder to hold the images of your article, the real docbook writing will be dropped under this sub-folder directly. 

Sounds tedious, don't worry, I create some easy things to help you on this:
	**mvn -Pcreate**
or 
	mvn -PcreateX -Dmodule=the path you want to create for your article

The former command will create a "tmpdir" under src/main/docbook, and copy article template and necessary images(addons and callout icons) to it, you can rename it after the command run. Of course, if you want to customize the name of the folder to be created, you can run the latter command.
	OK, that's for src/main/docbook folder.
	
### 2- src/main/resources  
I have collected necessary resources and put them under this folder, most of the time, you don't need to worry about these things.
	
### 3- src/main/assembly  
If you wan't to distributed your articles, you can customize assembly descriptor under this folder, of course, using the default is ok.
	
Since you have know everything necessary, and you may have put some docbook articles under the src/main/docbook folder, run "mvn package", after that, you can get your generated document under "target/docs/html" folder, What? Build Error? Find out the reason yourself by focusing on your docbook document structure and elements ;-)	
	
GL & HF	