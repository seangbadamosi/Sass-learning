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