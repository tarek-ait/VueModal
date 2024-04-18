- the node modules folder store any library we use any - -library we install is automatically stored there
- the public has our indexx.html project 
- the src folder is where we write our cdode , components css and all of them are gonna live there
- in the main.js we import the modules we want without using the .object
- the vue files are single file components 
- git ignore for those who wants to use github in there projects.
- the assets folder is for our images that we might use in our project 

**vue files and templates:

we have first the html template 
the script (optional) 
the style (optional)


** components 
we spit our code and components ( one for the navbar , the footer n the header ...) this help our code to be more readable
the app.vue component is the main component (sit on the top of the application ) and all the other components will nested on the app.vue component and we might have other subcomponents nested on the components (child components and parent components) and together they make a component tree (very important in the analysis of our project)


we create another vue file for our component 
we do the html inside the template tag
we do the styling 
now we have to import it (as we said that the app.vue is the main component what we must do is that we import the component in the script tag and give it a name and add that name to the component object in the export default then we will be able to use the component as an html tag in out app.vue template)
just start naming them with a capital letter to avoid problems with the html tags
for the styling we add 'scoped' in the tag style else it will effect on the app.vue and other components

displaying dynamic data on components (why , so they become more reusable)

for passing custom components into another components we use slots tags in the component