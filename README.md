<div align="center">

## Classes in PHP


</div>

### Description

This tutorial will walk you step by step on how to create and manage classes in PHP.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Dustin R Davis](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/dustin-r-davis.md)
**Level**          |Beginner
**User Rating**    |4.4 (70 globes from 16 users)
**Compatibility**  |PHP 4\.0
**Category**       |[Data Structures](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/data-structures__8-8.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/dustin-r-davis-classes-in-php__8-810/archive/master.zip)





### Source Code

<P>&nbsp;</P>
<table width="467" border="0" cellspacing="0" cellpadding="0">
 <tr>
  <td bgcolor="#ddddcc"><font color="#000000" size="2" face="Arial, Helvetica, sans-serif"><b>Introduction</b></font></td>
 </tr>
 <tr>
  <td>
   <p><font face="Arial, Helvetica, sans-serif" size="2">If you are coming
    to PHP from C++ then you can understand the need to OOP. But for the rest
    of you, OOP is, in my eyes, the greatest thing to come to programming.
    Classes allow you to keep track of a lot of information, and to also include
    function for manipulating that information.</font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2">I read something someone
    wrote and I related instantly. They said that OOP is hard to grasp, but
    once you understand the concept and the need, it's as bright as day. I
    could never understand why we needed classes until one day I was working
    on a project and it hit me.</font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2">So why do you need
    classes? Well, lets say you are making a game. In this game you have multiple
    players. Lets say for now that the limit is 8 players. You would have
    to type out and keep track of 8*x variables. x = number of attributes
    a player has.</font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2">Example:</font></p>
   <blockquote>
    <p><font face="Arial, Helvetica, sans-serif" size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">//Player
     1</font></b></font><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1"><br>
     P1_NAME;<br>
     P1_SCORE;<br>
     P1_AMMO;</font></b></font></p>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">//Player
     2<br>
     P2_NAME;<br>
     P2_SCORE;<br>
     P2_AMMO;</font></b></font></p>
   </blockquote>
   <p><font size="2" face="Arial, Helvetica, sans-serif">Now you would have
    to do this 8 times, so 8*3=24 variables you'd have to keep track of. Lets
    go on. Lets say Player 2 changed his name. You would have to create a
    if/else or a switch function to figure out what player he is, and then
    update his variables.</font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2">Example:</font></p>
   <blockquote>
    <blockquote>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">if(Player1)
      { </font></b></p>
     <blockquote>
      <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">P1_Name
       = NewName;</font></b></p>
     </blockquote>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">}
      else if(Player2) {</font></b></p>
     <blockquote>
      <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">P2_Name
       = NewName;</font></b></p>
     </blockquote>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">}</font></b></p>
    </blockquote>
   </blockquote>
   <p><font face="Arial, Helvetica, sans-serif" size="2">you'd have to do this
    for all 8 players. What a mess!</font></p>
  </td>
 </tr>
</table>
<br>
<table width="467" border="0" cellspacing="0" cellpadding="0">
 <tr>
  <td bgcolor="#ddddcc"><font color="#000000" size="2" face="Arial, Helvetica, sans-serif"><b>The
   OOP Method</b></font></td>
 </tr>
 <tr>
  <td align="left" valign="top">
   <p><font face="Arial, Helvetica, sans-serif" size="2">Lets take a look at
    that scenario from an OOP point of view.</font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2">You have a multi-player
    game. This time you want to allow 100 players. Now from the first example
    this would be a chore to keep track of all this information. But not with
    OOP! First, we make a class and define an array</font></p>
   <blockquote>
    <p><font face="Arial, Helvetica, sans-serif" size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">//Our
     class definition<br>
     Class cPlayer {</font></b></font></p>
    <blockquote>
     <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">//Our
      variables <br>
      var $Name;<br>
      var $Score;<br>
      var $Ammo;</font></b></font></p>
     <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">//Our
      functions <br>
      function ChangePlayerName($NewName) {</font></b></font></p>
     <blockquote>
      <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">$this-&gt;Name
       = $NewName;</font></b></font></p>
     </blockquote>
     <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">}</font></b></font></p>
    </blockquote>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">}
     </font></b></font></p>
   </blockquote>
   <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">$PlayerCount;<br>
    $Players[PlayerCount] = new cPlayer;</font></b></font></p>
   <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">//Lets
    change the name using OOP!<br>
    $Players[PlayerID]-&gt;ChangeName(&quot;Player3456&quot;);</font></b></font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2">Now how easy was that?
    Less code, allows for more dynamic code and saves space and time. Lets
    take a closer look at classes.</font></p>
  </td>
 </tr>
</table>
<br>
<table width="467" border="0" cellspacing="0" cellpadding="0">
 <tr>
  <td bgcolor="#ddddcc"><font color="#000000" size="2" face="Arial, Helvetica, sans-serif"><b>The
   Class frame</b></font></td>
 </tr>
 <tr>
  <td align="left" valign="top">
   <p><font size="2" face="Arial, Helvetica, sans-serif">You define a class
    by the <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">class</font></b>
    keyword, followed by the name of the class.</font></p>
   <blockquote>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">class
     cMyClass {</font></b></font></p>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">}</font></b></font></p>
   </blockquote>
   <p><font face="Arial, Helvetica, sans-serif" size="2">I put a 'c' in front
    of my class name, just so I know its a class. You can put what you like,
    but remember, the name has rules. You can not have a name beginning with
    a number, or use a name that has a space and you can not use a name that
    is already a keyword or a function name. </font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2">You define a variable
    of type <b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">cMyClass</font></b>
    like so:</font></p>
   <blockquote>
    <p><font face="Arial, Helvetica, sans-serif" size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">$myClass
     = new cMyClass;</font></b></font></p>
   </blockquote>
   <p><font face="Arial, Helvetica, sans-serif" size="2">This says that we
    want <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$myClass</font></b>
    to be of type <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cMyClass</font></b>.
    Now we can use <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$myClass</font></b>
    to access the variables inside of <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cMyClass</font></b>.</font></p>
  </td>
 </tr>
</table>
<br>
<table width="467" border="0" cellspacing="0" cellpadding="0">
 <tr>
  <td bgcolor="#ddddcc"><font color="#000000" size="2" face="Arial, Helvetica, sans-serif"><b>The
   Class guts - Variables</b></font></td>
 </tr>
 <tr>
  <td align="left" valign="top">
   <p><font size="2" face="Arial, Helvetica, sans-serif">Having a class is
    no good if you don't have something inside of it. So with this in mind,
    we add some variables. To add variables, we first identify the variable
    by putting the<b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">
    var</font></b> keyword in front of our variable name.</font></p>
   <blockquote>
    <p><font size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">class
     cMyClass {</font></b></font></p>
    <blockquote>
     <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">var
      $myVariable;</font></b></font></p>
    </blockquote>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">}</font></b></font></p>
   </blockquote>
   <p><font size="2" face="Arial, Helvetica, sans-serif">Now we have a variable
    that we can access. To access this variable you can use the variable we
    defined for <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cMyClass</font></b>.</font></p>
   <blockquote>
    <p><font size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">$myClass-&gt;myVariable
     = &quot;My Class&quot;;</font></b></font></p>
   </blockquote>
   <p><font size="1" face="Arial, Helvetica, sans-serif"><b><font face="Verdana, Arial, Helvetica, sans-serif">$myVariable</font></b></font><font size="2" face="Arial, Helvetica, sans-serif">
    inside of <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cMyClass</font></b>
    is now set to <i>&quot;My Class&quot;</i>. Now, lets say we want to view
    what is in the variable. You'd assume (as I did) that you can do it this
    way</font></p>
   <blockquote>
    <p><font size="1" face="Verdana, Arial, Helvetica, sans-serif"><b>echo
     $myClass-&gt;myVariable;</b></font></p>
   </blockquote>
   <p><font size="2" face="Arial, Helvetica, sans-serif">Well, unfortunately,
    this does not work. Those coming from C++ will be disappointed to hear
    that you will need to define a function inside of the class to print the
    value of the variable. See the next section for functions.</font></p>
  </td>
 </tr>
</table>
<br>
<table width="467" border="0" cellspacing="0" cellpadding="0">
 <tr>
  <td bgcolor="#ddddcc"><font color="#000000" size="2" face="Arial, Helvetica, sans-serif"><b>The
   Class guts - Functions / Constructors</b></font></td>
 </tr>
 <tr>
  <td align="left" valign="top">
   <p><font size="2" face="Arial, Helvetica, sans-serif">The ability to have
    functions that are specific to your class is great. It is also needed.
    The first function we will talk about will be the <b><i>constructor</i></b>.
    The constructor is a function that gets called when we create a variable
    defined as being of type <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cMyClass</font></b>.
    This constructor function has the same name as the class.</font></p>
   <blockquote>
    <p><font size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">class
     cMyClass {</font></b></font></p>
    <blockquote>
     <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">var
      $myVariable;</font></b></font></p>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">function
      cMyClass() {</font></b></p>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">}</font></b></p>
    </blockquote>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">}</font></b></font></p>
   </blockquote>
   <p><font size="2" face="Arial, Helvetica, sans-serif">So what do we do with
    this constructor? Well, nothing if you dont need it. But, lets say that
    you want to define <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$myVariable</font></b>
    as having a default value.</font></p>
   <blockquote>
    <p><font size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">class
     cMyClass {</font></b></font></p>
    <blockquote>
     <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">var
      $myVariable = &quot;This is a default value&quot;;</font></b></font></p>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">function
      cMyClass() {</font></b></p>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">}</font></b></p>
    </blockquote>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">}</font></b></font></p>
   </blockquote>
   <p><font size="2" face="Arial, Helvetica, sans-serif">This does not work.
    It will give an error. So this is where our constructor functions comes
    in. We can set the default value of <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$myVariable</font></b>
    inside this function.</font></p>
   <blockquote>
    <p><font size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">class
     cMyClass {</font></b></font></p>
    <blockquote>
     <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">var
      $myVariable;</font></b></font></p>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">function
      cMyClass() {</font></b></p>
     <blockquote>
      <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">
       $this-&gt;myVariable = &quot;This is a default value&quot;;</font></b></font></p>
     </blockquote>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">}</font></b></p>
    </blockquote>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">}</font></b></font></p>
   </blockquote>
   <p><font face="Arial, Helvetica, sans-serif" size="2">Now, when we define
    <font face="Verdana, Arial, Helvetica, sans-serif"> <font size="1"> <b>$myClass
    = new cMyClass;</b></font></font> our constructor will be called and the
    value of <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$myVariable</font></b>
    will be set.</font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2">Creating your own
    functions is just as easy. Just identify our function by putting the <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">function</font></b>
    keyword in front of the function name.</font></p>
   <blockquote>
    <p><font size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">class
     cMyClass {</font></b></font></p>
    <blockquote>
     <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">var
      $myVariable;</font></b></font></p>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">function
      cMyClass() {</font></b></p>
     <blockquote>
      <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">
       $this-&gt;myVariable = &quot;This is a default value&quot;;</font></b></font></p>
     </blockquote>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">}</font></b></p>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">function
      MyFunction() {</font></b></p>
     <blockquote>
      <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">return
       $this-&gt;myVariable; </font></b></p>
     </blockquote>
     <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">}</font></b></p>
    </blockquote>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">}</font></b></font></p>
   </blockquote>
   <p><font face="Arial, Helvetica, sans-serif" size="2">in our new function
    that we just defined, we return the value of <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$myVariable</font></b>.
    Now, you should have a good understanding of how we add functions and
    variables. Lets take a look at how to access these class members.</font></p>
  </td>
 </tr>
</table>
<br>
<table width="467" border="0" cellspacing="0" cellpadding="0">
 <tr>
  <td bgcolor="#ddddcc"><font color="#000000" size="2" face="Arial, Helvetica, sans-serif"><b>Accessing
   class members</b></font></td>
 </tr>
 <tr>
  <td align="left" valign="top">
   <p><font size="2" face="Arial, Helvetica, sans-serif">You access class members
    by using the <b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">-&gt;</font></b>
    symbol.</font></p>
   <blockquote>
    <p><font size="2" face="Arial, Helvetica, sans-serif"><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$myClass-&gt;myVariable;</font></b></font></p>
   </blockquote>
   <p><font size="2" face="Arial, Helvetica, sans-serif">When accessing class
    members, you do not need to include the <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$</font></b>
    infront of variable names.</font></p>
   <blockquote>
    <p><font face="Arial, Helvetica, sans-serif" size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">$myClass-&gt;$myVariable
     = &quot;This is wrong&quot;;</font></b></font></p>
    <p><font face="Verdana, Arial, Helvetica, sans-serif"><b><font size="1">$myClass-&gt;myVariable
     = &quot;This is correct&quot;;</font></b></font></p>
   </blockquote>
   <p><font face="Arial, Helvetica, sans-serif" size="2">When accessing class
    members from inside the class, you will need to use the <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$this</font></b>
    keyword. Follow the same rules as above when accessing the class members
    from inside the class.</font></p>
   <blockquote>
    <p><font face="Verdana, Arial, Helvetica, sans-serif" size="1"><b>$this-&gt;myVariable
     = &quot;Accessing it from inside&quot;;</b></font></p>
   </blockquote>
   <p><font face="Arial, Helvetica, sans-serif" size="2">Accessing our members
    is not hard. You just need to know how.</font></p>
  </td>
 </tr>
</table>
<br>
<table width="467" border="0" cellspacing="0" cellpadding="0">
 <tr>
  <td bgcolor="#ddddcc"><font color="#000000" size="2" face="Arial, Helvetica, sans-serif"><b>Nested
   classes </b></font></td>
 </tr>
 <tr>
  <td align="left" valign="top">
   <p><font face="Arial, Helvetica, sans-serif" size="2">At some point, you
    will want to have nested classes. Nested classes are classes defined inside
    another class. Take a look at this example:</font></p>
   <blockquote>
    <p><font size="1" face="Verdana, Arial, Helvetica, sans-serif"><b>class
     cMyClass {</b></font></p>
    <blockquote>
     <p><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">var
      $myVariable;</font></b></p>
     <p><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">function
      cMyClass() {</font></b></p>
     <blockquote>
      <p><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$this-&gt;myVariable
       = &quot;Hello&quot;;</font></b></p>
     </blockquote>
     <p><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">}</font></b></p>
     <p><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">function
      MyFunction() {</font></b></p>
     <blockquote>
      <p><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">return
       $this-&gt;myVariable;</font></b></p>
     </blockquote>
     <p><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">}</font></b></p>
    </blockquote>
    <p><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">}</font></b></p>
    <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">class
     cNewClass {</font></b></p>
    <blockquote>
     <p><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">var
      $newVariable;<br>
      var $myClass;</font></b></p>
     <p><font size="1" face="Verdana, Arial, Helvetica, sans-serif"><b>function
      cNewClass() {</b></font></p>
     <blockquote>
      <p><font size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">
       $newVariable = &quot;Nothing for now&quot;;</font></b></font><br>
       <b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">$myClass
       = new cMyClass;</font></b></p>
     </blockquote>
     <p><font size="1" face="Verdana, Arial, Helvetica, sans-serif"><b>}</b></font></p>
     <p><font size="1" face="Verdana, Arial, Helvetica, sans-serif"><b>function
      NewFunction() {</b></font></p>
     <blockquote>
      <p><font size="1"><b><font face="Verdana, Arial, Helvetica, sans-serif">
       $newVariable = $this-&gt;myClass-&gt;MyFunction();</font></b></font></p>
     </blockquote>
     <p><font size="1" face="Verdana, Arial, Helvetica, sans-serif"><b>}</b></font></p>
    </blockquote>
    <p><b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">}</font></b></p>
   </blockquote>
   <p><font face="Arial, Helvetica, sans-serif" size="2">Now to sort out your
    confusion. What happened here was this, first, we defined our class <b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">cMyClass</font></b>.
    Then we define our new class <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cNewClass</font></b>.
    Inside of <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cNewClass</font></b>
    we defined a variable <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$myClass</font></b>.
    Then in the constructor for <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cNewClass</font></b>
    we decalred <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">myClass</font></b>
    as <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cMyClass</font></b>.
    Now, we have access to the members of <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cMyClass</font></b>
    from <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cNewClass</font></b>.</font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2">In our <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">NewClass</font></b>
    function we set our <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$newVariable</font></b>
    to the value of <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cMyClass</font></b>.
    We do this by calling the member function <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">MyFunction()</font></b>
    of <b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">cMyClass</font></b>
    to return the value of <b><font face="Verdana, Arial, Helvetica, sans-serif" size="1">myVariable</font></b>.
    You can also do this from outside of the class like so:</font></p>
   <p><font face="Arial, Helvetica, sans-serif" size="2"><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">$NewClass
    = </font><font face="Arial, Helvetica, sans-serif" size="2"><b><font size="1" face="Verdana, Arial, Helvetica, sans-serif">new
    cNewClass;<br>
    <br>
    $NewClass-&gt;newVariable = $NewClass-&gt;myClass-&gt;MyFunction();</font></b></font></b></font></p>
   </td>
 </tr>
</table>
<br>
<table width="467" border="0" cellspacing="0" cellpadding="0">
 <tr>
  <td bgcolor="#ddddcc"><font color="#000000" size="2" face="Arial, Helvetica, sans-serif"><b>Conclusion</b></font></td>
 </tr>
 <tr>
  <td align="left" valign="top"><font size="2" face="Arial, Helvetica, sans-serif">Hopefully
   I didn't leave out too much information. I tried to cover the basics. OOP
   is such a great thing that if you are not using it, you are missing out.
   It allows for easy coding and also allows for more dynamic coding. If you
   don't understand OOP, I suggest learning.</font></td>
 </tr>
</table>

