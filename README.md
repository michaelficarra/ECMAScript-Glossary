### A shared vocabulary for people who need to talk about ECMAScript.

I am a personal believer in the supreme importance of a shared vocabulary among
collaborators on *any* project in *any* field. The first step in any project is
understanding how to communicate about the problem and communicate details of
the problem itself. For the general domain of problems being solved with
ECMAScript, it would be nice to have a vocabulary that exists outside of the
group with whom you work most closely. For this reason, I've been trying to use
a consistent and unambiguous vocabulary when discussing issues in OSS projects
I like to work on for... years. But I don't feel this is enough. So I've taken
the time to start formally defining a vocabulary that can be shared among all
developers working on ECMAScript projects. It's nowhere near comprehensive yet,
so feel free to open up an issue. If you work on ECMAScript projects, try to
adopt these terms into your own vocabulary, and use them when speaking with
your team. Hopefully we can foster an environment where communicating with
people you've never worked with becomes at least a little bit easier.

## Glossary

<dl>
<dt><a name="apply"/>apply
  <dd>See <a href="#function-application">function application</a>.
<dt><a name="argument"/>argument [list]
  <dd>An expression (or comma-separated list of expressions) provided to a function during <a href="#function-application">function application</a>.
<dt><a name="callable"/>callable
  <dd>An object is callable if it implements the internal <code>[[Call]]</code> method and therefore may be <a href="#function-application">applied</a>. All functions are callable.
<dt><a name="call"/>call
  <dd>See <a href="#function-application">function application</a>.
<dt><a name="class"/>class
  <dd>Has no meaning in ECMAScript (as of <a href="#ES5">ES5</a>). In CoffeeScript, "class" refers to a constructor that was defined using a special syntactic form.
<dt><a name="CoffeeScript"/>CoffeeScript
  <dd>A programming language that shares many of its semantics with ECMAScript.
<dt><a name="constructor"/>constructor
  <dd>An object (almost always a function) with an internal <code>[[Construct]]</code> method and "prototype" <a href="#property">property</a> that is intended to be used as the prototype of another object. This can be done either through use of the <code>new</code> operator (in which case the constructor will be <a href="#function-application">applied</a>) or through <code>Object.create</code>.
<dt><a name="constructor-method"/>constructor method
  <dd>A <a href="#method">method</a> of a <a href="#constructor">constructor</a>.
<dt><a name="constructor-property"/>constructor property
  <dd>A <a href="#property">property</a> of a <a href="#constructor">constructor</a>.
<dt><a name="context"/>context
  <dd>The value of <code>this</code>.
<dt><a name="cyclic-object"/>cyclic object
  <dd>An object that cannot be modeled as a <a href="http://en.wikipedia.org/wiki/Directed_acyclic_graph">DAG</a> because of the possibility of a series of one or more member accesses creating a cycle. See also <a href="#cyclic-object">cyclic object</a>.
<dt><a name="declared"/>declared
  <dd>An identifier is declared if a lookup in the scope chain would be successful. In other words, a bare reference to it (outside <code>typeof</code>) will not cause a <code>ReferenceError</code> to be thrown. The identifier need not enter scope through a variable declaration; <a href="#parameter">parameter</a> names, <a href="#named-function-expression">NFE</a> name, <a href="#function-declaration">FD</a> names, and <a href="#property">property</a> assignment of any member of the scope chain will all cause an identifier to be declared.
<dt><a name="defined"/>defined
  <dd>See <a href="#undefined">undefined</a>.
<dt><a name="dynamic-member-access"/>dynamic member access
  <dd>A <a href="#member-access">member access</a> performed using the postfix <code>[]</code> syntactic form. May not qualify as "dynamic" if the value used within <code>[]</code> is able to be statically determined.
<dt><a name="ES3"/>ES3
  <dd>ECMAScript, as defined in version 3.
<dt><a name="ES5"/>ES5
  <dd>ECMAScript, as defined in version 5. Often used to refer to the latest revision, currently 5.1.
<dt><a name="eval"/>eval
  <dd>evil
<dt><a name="falsey"/>falsey
  <dd>Any expression that evaluates to a member of the set {<a href="#undefined-value"><code>undefined</code> value</a>, <code>null</code>, <code>false</code>, <code>0</code>, <code>-0</code>, <a href="#NaN-value"><code>NaN</code> value</a>, <code>""</code>}.
<dt><a name="FD"/>FD
  <dd>See <a href="#function-declaration">function declaration</a>.
<dt><a name="function-application"/>function application
  <dd>Causing a <a href="#callable">callable</a> object to execute with a given <a href="#argument">argument list</a>.
<dt><a name="function-call"/>function call
  <dd>See <a href="#function-application">function application</a>.
<dt><a name="function-declaration"/>function declaration
  <dd>A <a href="#named-function-expression">named function expression</a> in statement position.
<dt><a name="function-expression"/>function expression
  <dd>A function literal in expression position. May or may not be named.
<dt><a name="function-invocation"/>function invocation
  <dd>See <a href="#function-application">function application</a>.
<dt><a name="global"/>global
  <dd>A <a href="#property">property</a> of <a href="#gobal-object">the gobal object</a>.
<dt><a name="global-object"/>[the] global object
  <dd>A special object that serves as the root of every scope chain and the <a href="#context">context</a> of code executed in the global environment (outside any function body).
<dt><a name="hoisting"/>hoisting
  <dd>The treatment of a statement within a lexical environment as if it had prefixed the non-hoisted statements. In ECMAScript, variable declarations (without their optional initialisations) and <a href="#function-declarations">function declarations</a> are hoisted.
<dt><a name="IIFE"/>IIFE
  <dd>See <a href="#immediately-invoked-function-expression">immediately-invoked function expression</a>.
<dt><a name="immediately-invoked-function-expression"/>immediately-invoked function expression
  <dd>A <a href="#function-expression">function expression</a> used as the target of <a href="#function-application">function application</a>.
<dt><a name="Infinity-value"/>Infinity value
  <dd><code>1/0</code>
<dt><a name="inherited-property"/>inherited property
  <dd>A <a href="#property">property</a> that does not exist on the object being described, but on one of the objects in its prototype chain. Not an <a href="#own-property">own property</a>.
<dt><a name="invoke"/>invoke
  <dd>See <a href="#function-application">function application</a>.
<dt><a name="JavaScript"/>JavaScript
  <dd>A superset of ECMAScript, designed and implemented by <a href="http://mozilla.org/">Mozilla</a>.
<dt><a name="member"/>member
  <dd>An object member, which is a mapping from a string to some value. The member may exist on the object itself or any of the objects in its prototype chain.
<dt><a name="member-access"/>member access
  <dd>A <a href="#property">property</a> lookup via either the infix <code>.</code> or postfix <code>[]</code> operators.
<dt><a name="method"/>method
  <dd>A <a href="#property">property</a> that is also a function. Those wishing to refer to the superset of methods that is <a href="#callable">callable</a> <a href="#property">properties</a> should use that more explicit term instead.
<dt><a name="named-function-expression"/>named function expression
  <dd>A <a href="#function-expression">function expression</a> that must have a name.
<dt><a name="NaN-value"/>NaN value
  <dd><code>0/0</code>
<dt><a name="NFE"/>NFE
  <dd>See <a href="#named-function-expression">named function expression</a>.
<dt><a name="parameter"/>parameter [list]
  <dd>An identifier (or comma-separated list of identifiers) used in the definition of a function. At runtime, the value of each parameter becomes the value that coordinates positionally with the <a href="#argument">argument list</a> given during <a href="#function-application">function application</a>.
<dt><a name="own-property"/>own property
  <dd>A <a href="#property">property</a> that exists on the object being described. Not an <a href="#inherited-property">inherited property</a>.
<dt><a name="property"/>property
  <dd>See <a href="#member">member</a>.
<dt><a name="truthy"/>truthy
  <dd>Any expression that is not <a href="#falsey">falsey</a>.
<dt><a name="undefined"/>undefined
  <dd>An unfortunately ambiguous term; instead, use <a href="#declared">undeclared</a> or "<a href="#undefined-value"><code>undefined</code> value</a>".
<dt><a name="undefined-value"/>undefined value
  <dd>A special value which is the initial value of the "undefined" <a href="#property">property</a> of the <a href="#global-object">global object</a>. This value is the same one created by applying a function that reaches the end of its execution without arriving at a <code>return</code> statement or performing a <a href="#member-access">member access</a> on an object where neither it nor the objects in its prototype chain contain the member.
<dt><a name="unnamed-function-expression"/>unnamed function expression
  <dd>A <a href="#function-expression">function expression</a> that must not have a name.
</dl>
