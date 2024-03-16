**React Js:**

**\#\# Must learn concepts before giving a react interview :**  
  
Life cycle methods of components:  
=======================  
3 phases and their methods  
  
Hooks:  
========  
useState  
useEffect  
useContext  
useReducer  
useMemo  
useCallback  
useRef  
  
Virtual dom:  
=========  
Reconciliation  
Diffing algorithm  
Render  
  
SSR and CSR  
============  
Difference and benifit, SEO, Performance  
  
Higher Order components:  
===================  
What is hoc, Why we use , When we use, How we use them ?  
  
State management  
=============  
State  
Props  
Props driling  
Context api  
Redux and toolkit  
  
CustomHooks  
==========  
When to use them and example code.  
  
LazyLoading:  
=========  
code splitting  
Suspense  
chunking  
  
Routing  
================  
react-router  
protected routes  
query params  
Dynamic routing  
Role based access control  
  
Testing:  
==================  
unit testing - Jest  
  
Async tasks  
==================  
Api calls  
fetch, axios  
events - scrolling  
  
Reusability, Modularity, Testability and Readability  
  
Performance:  
============  
lazyloading  
optimize assets,js,css  
Bundlers  
How to make rendering components fast and optimized?  
  
Styling:  
===============  
Bootstrap,Material Ui  
Css,scss,inline styling  
  
Accessibility  
Security

**redux ko use krny ka treqa--\>**

1 create store 2 wrap app component in index.js with provider tag,es provider ko
btana b h knsa store use krna h so ek prop es me write kre gy asy store={name of
store}3es k bd slice create krna h jo k ek function using createslice
function,es m initial state ko set kr skty hn separately b aur phr usko yaha
assign kr dy gy ya esi k andr aur eska name b set krty hn ,aur reducers define
krty hn jo k basically functions huty hn jo state ko change krny kliy use huty
hn aur phr end pe en sb reducers ko export krna huta h using slicename.actions
aur phr es k bd store m ek reducer property huti h usko ja kr jo reducer bnaya
huga assign kr dy gy aur esko json me likhna h jo name property use ki thi
reducer m wo aur esko phr jo reducer ka name dy gy es file m wo assign kr dy gy
q k jaha esko import kiya jaay ga waha koi b eska name rakh skty hn aur phr usko
assign kr dy gy aesa krny se he store m states aa sky gi aur phr unko access kr
sky gy

4 ab jis component m b state ko use krna h us kliy useselector hook ka use kry
gy aur phr he us state ko access kr paay gy asy likhna h useselector
(stateobject variable)=\>(stateobject variable. reducername.statename)

5ye tha state ko access krna hu tu but agr state ko change krna hu tu phr
dispatch ka use krty hn tu es kliy actions ko import kre gy aur enko phr
usedispatch m use kr dy gy ,es kliy pehly eska object create kr le aur call back
function m dispatch object ko action pass kr dy gy but ye action ko pehly import
b krna h, that's the use of reduc

**A-aur esi store m aur b bht c states ko store kiya ja skta procedure yahe same
rahega sb kliy**

**B-aur ye redux tb use krty hn jb state ko globally sb components ko pass krna
hu,usestate jb ek feature ya component m state ko change krna hu, context API b
us kr skty hn but us m state ko uplift krna prta h children se parent ko aur phr
parent se us particular component ko assign kr dy gy,aesa krny m issue ye huta h
k un components m b state ko import krna prta h jaha use ni krna huta esko aur
code increase huta h aur performance weak huti h**

**Dependencies:**

dependencies that is required for the software to be run .i.e bootstrap ka add
krna project me aur phr project ko server pe tun krvaany kliy b tu ye chaay hugi
warna software responsive ni rahega ,ye mtlb dependency packages ka collection b
hu skti h aur esko agr version k saath le kr chlna hu aur bki sb team k saath tu
phr npm ko use kiya ja skta h

**Material UI:**

import React from 'react';

import { makeStyles } from '\@material-ui/core/styles';

import Button from '\@material-ui/core/Button';

const useStyles = makeStyles({

root: {

background: 'linear-gradient(45deg, \#FE6B8B 30%, \#FF8E53 90%)',

border: 0,

borderRadius: 3,

boxShadow: '0 3px 5px 2px rgba(255, 105, 135, .3)',

color: 'white',

height: 48,

padding: '0 30px',

},

});

export default function Hook() {

const classes = useStyles();

return \<Button className={classes.root}\>Hook\</Button\>;

}

As you can see in this example, we're using the makeStyles function to generate
a hook called useStyles which create a CSS classes object which contains the
keys of the styles object we created. In this example, it doesn't actually
matter that we call this class root, because we reference it like a variable
when we add it to the Button's className prop. As you will read in the advanced
customization guide:

Every component provides a className property which is always applied to the
root element.

That's so important! That means we can always safely overwrite the root
element's CSS. In this above example, we are changing the Button's background
color, height, text color. Did you know that the Button is just a simple HTML
\<button\> tag with a \<span\> for the text? There's a simplicity to underlying
HTML that you should get to know.

This is pretty much it, taken from a contained Button example:

\<button class="MuiButtonBase-root MuiButton-root MuiButton-contained
MuiButton-containedPrimary" tabindex="0" type="button"\>

\<span class="MuiButton-label"\>Primary\</span\>

\<span class="MuiTouchRipple-root"\>\</span\>

\</button\>

How to style inner HTML elements in Material UI

Okay so you might be wondering, how to I know how to target these inner HTML
elements of Material UI? Where is this documented? Welcome to CSS rules! Let's
quote from the "Overriding styles with classes" section. Read the following very
closely!

When the className property isn't enough, and you need to access deeper
elements, you can take advantage of the classes object property to customize all
the CSS injected by Material-UI for a given component. The list of classes for
each component is documented in the component API page, you should refer to the
CSS section and rule name column. For instance, you can have a look at the
Button CSS API. Alternatively, you can use the browser dev tools.

To summarize, you can find the names of the CSS rules in the second half of the
component's API page. For the Button, you can see that there is a root rule, and
a label rule. If you're too lazy to go to the API page and just want to inspect
the HTML, you can see above that there is a -label rule right on the \<span\>
element. Target that rule by using the classes prop with an object containing
those keys from your classes you got from useStyles.

That looks like this:

\<Button

classes={{

root: classes.root, // class name, e.g. classes-nesting-root-x

label: classes.label, // class name, e.g. classes-nesting-label-x

}}

\>

classes nesting

\</Button\>
