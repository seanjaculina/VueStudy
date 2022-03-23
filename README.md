# StudyVue

1) Used CLI - 'vue create vue-crashcourse'

-- Personal Notes --

2) App.vue
    - Template is the output/HTML
    - script is the logic
    - style is the styling for the page

3) To use a component, must be defined within the components object. Then may be passed to the template to be displayed.

4) scoped within the tag means this is only for this 
specific components scope 

5) Added life cycle method to App.vue
- added hard coded array of objects inside of created method initially for learning purpose, will pull from an API shortly.
 - when a component is loaded it goes through a specific life cycle where certain methods are fired off and you may hook into to do specific things are certain times.
 - using life cycle method, created.
    - used for HTTP requests
    - load data when your page or component loads.


6) emitting upwards to App.vue from Task.vue to allow deletion of a task
$emit = send custom events from a child component to its parent.
this.$emit('delete-task', task.id)
