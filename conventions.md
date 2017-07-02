## Naming

* Everything in camelCase, to the exception of file names in kebab-case.
* Do not repeat the context : ie: the function "get" of DojoService should be called "get", not "getDojo"
  * Unless it's unclear, in which case you should probably split into a different file to make the context explicit

## **CSS**

Please use BEM. See [http://getbem.com/naming/](http://getbem.com/naming/) for reference

Required fields : do not use asterisk, instead use "optional" for optional fields, the rest becomes "mandatory"

* less clusters of stars
* less problem with translation \(ltr, asterisk in translation\)
* src : [http://uxmovement.com/forms/why-users-fill-out-less-if-you-mark-required-fields/](http://uxmovement.com/forms/why-users-fill-out-less-if-you-mark-required-fields/)

Select fields :

* should have a default non-reselectable value for non-required fields
* shouldnt' have a default value if it's required \([https://www.nngroup.com/articles/form-design-placeholders/\](https://www.nngroup.com/articles/form-design-placeholders/\)\)

## Wording

Form process of creation :

* ask questions or affirmative ?



