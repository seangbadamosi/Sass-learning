# Sass-Learning
### Lesson 1 | Variables
* If you know a bit of Js then you should be familar with variables
* To create a varible you write a dollar sign (\$) then give it a name then you can assign it a css property-value eg

```{scss}
    $primary-btn: red;

    a{
        background-color:$primary-btn;
    }
```
* It helps to avoid repetition if there is a problem with a specific code you simply change the value of the variable, and any tag with a matching variable value will change 
* When crearting a variable you write at the top of the scss like line 1, 2 and 3
 
 ### Lesson 2 | Nesting
 * it helps reflect the html structure and makes the styling more readable and easy to maintain this can be done in plain css
 * Related styles are grouped together, making the code more organized eg
 ```{scss}
    header{
    background-color: lightblue;
    display: flex;
    justify-content: center;
    align-items: center;
    color: $textColor;
    height: 15vh;

    button{
        background-color:  $primaryBtn;
        transition: 2s;
        border-radius: 10px;
        width: 10vw;
        height: 6vh;
        text-transform: capitalize;
        
        &:hover{
            background-color: red;
        }
        
        &::after{
            content: 'ooo';
        }
    }
}

 ```
* this is how it looks like with nesting 
* nesting allows you to put slectors into one another creating a type of hierarchy and making it more readable
* we should be cautious not to nest more than three levels that is greatgrandparents, grandparents,  parents and child we should avoid 👎
it  

### Lesson 3 | Import
* @import as it is is commonly written, @import allows you to include the contents of one SCSS file into another
* we should remember to add underscore (_) to any partial file the underscore lets Sass know that the file is only a partial file and that it should not be generated into a CSS file.
* @import is a directive not a variable, function or keyword it is added is added to the main scss file written after the variables (that is if the varaibles are in the same file as the main scss file )
* the order at which you import is important like importing footer.scss before header.scss will make the footer show before the header in css 
* example of an import eg
```{scss}
1   @import ' ./variables';
2   @import ' ./header';
3   @import ' ./footer';
```

### Lesson 4 | Mixins and Include
* A mixin in scss is a reusable block of css code that allows you to define a set of styles once and then add the directive "include" in different parts of your stylesheet ( like a function in Js)
* by writing @mixin at the top of your scss file you write css properties in it give the mixin a name give it parentheses () to link it with the tag or selector you want it to affect, you write @include with the name of the mixin and parentheses also add semi-column here is an example below
```{scss}
    @mixin flexEnd(){ 👈
        display: flex;
        justify-content: end;
        align-items: center;
    }

    
main{
    height: 55vh;
    margin: 20vh 0 0 0;
    @include flexEnd(); 👈

    .contact button{
        background-color:  $primaryColor;
        border-radius: 10px;
        width: 10vw;
        height: 6vh;
        text-transform: capitalize;
    }
}
```
* mixins and include can also work in all the partial scss not just the main file, if they have the directive of @import
* a, the name of the mixin should be in camel case that is the words should not be spaced there is example below 👇 
* b, mixin can carry parameters or inputs 👇  
```{scss}    
                👇
   a, @mixin flexCenter(){}

   b, @mixin flexCenter ($textTransform, $color) {
        display: flex;
        justify-content: end;
        align-items: center;
        text-transform: $textTransform;
        color: $color;
    }

        header{
    @include flexCenter(capitalize, blue);
    background-color: lightblue;
    height: 15vh;

    button{
        background-color:  $primaryColor;
        transition: 2s;
        border-radius: 10px;
        width: 10vw;
        height: 6vh;
        text-transform: $textTransform;
        margin: 0 0 0 10px;
        color: $color;
        }   
    }
```

`Note in this readme.md file my mentioning of js means JavaScript`

### Lesson 5 | Extend
* extend is a directive 
* it helps to reduce repetitive code examples below
```{scss}
    .button {
  padding: 10px 20px;
  background-color: blue;
  color: white;
  border-radius: 5px;
}

.primary-button {
  @extend .button;
  background-color: green; /* Overrides background-color */
}

.secondary-button {
  @extend .button;
  background-color: gray; /* Overrides background-color */
}
```
* @extend as is commonly used is used to share a set of CSS properties from one selector with another selector.



