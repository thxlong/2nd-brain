

Here two aspects have to be distinguished:

1. First and foremost it's important to understand the difference between the notation with and without brackets in general, independent of **[ngClass]** or **[ngStyle]**:

**Without** squared brackets Angular **interprets** the content between the quotation marks as a string (just as it is).

**With** squared brackets Angular tries to **evaluate** the expression between the quotation marks to a string.

-----

Written in pseudo code the general difference of these two notations could be illustrated like this:

Interpret as string: **name="Max"**

Evaluate to string: **[name]="callTheNameOnTheDoorbellLabel()"**

Evaluate to string: **[name]="'M' + 'a' + 'x'"**

Evaluate to string: **[name]="'Max'"** _(not very useful, but possible)_

-----

The built-in directives ngClass and ngStyle are always used **with** brackets:

→ [https://angular.io/api/common/NgClass#usage-notes](https://angular.io/api/common/NgClass#usage-notes "Click here!")

→ [https://angular.io/api/common/NgStyle#usage-notes](https://angular.io/api/common/NgStyle#usage-notes "Click here!")

When used **without** brackets they would just have the same effect like a normal **class** or **style** attribute in HTML:

`**<div ngClass="...">** is the same as **<div class="...">**`

`**<div ngStyle="...">** is the same as **<div style="...">**`

An Example:

1.  `<div [ngStyle]="{backgroundColor: condition ? 'yellow' : 'red'}">Red or yellow? - that depends!</div> `
2.  `<div style="background: limegreen">Always limegreen!</div>`

2. These are the two equivalent **ngIf**-notations:

Under the hood this directive is always placed on an **ng-template**, modifiying its inner structure:

1.  `<ng-template [ngIf]="condition">`
2.   `<div>To be, or not to be - that is the question</div>`
3.  `</ng-template>`

For convenience only there is this shorter notation, which will be used in practice in most cases:

1. ` <div *ngIf="condition">To be, or not to be - that is the question</div> `

Both are equivalent, the second one is just syntactic sugar.

Max explains the difference in this lecture:

→ [https://www.udemy.com/the-complete-guide-to-angular-2/learn/v4/t/lecture/6656182?start=0](https://www.udemy.com/the-complete-guide-to-angular-2/learn/v4/t/lecture/6656182?start=0 "Click here!")

And he shows in the next lecture that you can do exactly the same with custom directives (***appUnless** vs. **[appUnless]**).