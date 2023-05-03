Download Link: https://assignmentchef.com/product/solved-cs-52-assignment-6
<br>
<strong>Background:</strong>In C++, many of the keyboard symbols that are used between two variables can be given a new meaning.  This feature is called operator overloading and it is one of the most popular C++ features.  Any class can choose to provide a new meaning to a keyboard symbol.  Not every keyboard letter is redefinable in this way, but many of the ones we have encounted so far are, like + and – and * and / and &gt; and &lt;, for example.  It is a class’ choice to do this, so mostly it is viewed as a driver code convenience to support them.  But because so many of us have an assumption that + should do addition but also perform string concatenation when working with textual data.  Each operator becomes a friend function in C++ that your class can implement.  The arguments to most of the operator overloads are defined as const FlashDrive &amp;.  This syntax is a new kind of parameter passing called const-reference parameters.  For a classtype, like FlashDrive, const &amp; signifies a read-only argument that cannot be changed by the function that receives this object.  The compiler enforces this restriction and, for classes, const &amp; simulates a pass-by-value mechanism without the overhead of copying the object, which might take a tremendous amount of time away from our program.  Read the book and demo source examples carefully to see how this is done.  Trust me, the first time you work with operators in C++, it is a very error-prone process.  My best advice to you is to complete one operator at a time.

<h3><strong>part_a: flashdrive 2.0</strong></h3>

<h3>Using flashdrive_2_0.cpp,  enhance the FlashDrive class so that it supports the operators +, -, &lt; and &gt;.  A sample pile of driver code is shown below to assist you in this effort.  Operators + and – should create a new FlashDrive from the two arguments by combining their contents.  If you wind up with a FlashDrive with a value stored that exceeds its capacity, print out an error message.  If you wind up with a negative capacity or storage value, print out an error message.   Operators &lt; and &gt; must return bool and should compare the holdings of the two arguments to determine which one is bigger.</h3>

My strong advice is to work one operator at a time, as these steps are very error-prone and lead to many, many compile errors.

Finally, I would also like you to place FlashDrive in namespace cs52 which will affect the resulting driver code as well as the class’ .h and .cpp files.

<table border="2" width="98%" rules="cols" cellspacing="0" cellpadding="2">

 <colgroup>

  <col width="95*">

  <col width="3*">

  <col width="159*">

 </colgroup>

 <tbody>

  <tr>

   <td width="37%"><strong>FlashDrive</strong></td>

   <td width="62%"><strong>Sample Driver Code</strong></td>

  </tr>

 </tbody>

 <tbody>

  <tr>

   <td width="37%">FlashDrive( );FlashDrive( int capacity, int used, bool pluggedIn );void plugIn( );void pullOut( );void writeData( int amount );void eraseData( int amount );void formatDrive( );int getCapacity( );void setCapacity( int amount );int getUsed( );void setUsed( int amount );bool isPluggedIn( );</td>

   <td rowspan="3" width="62%">#include &lt;iostream&gt;#include “FlashDrive.h”using namespace std;using namespace cs52;void main( ){cs52::FlashDrive drive1( 10, 0, false );cs52::FlashDrive drive2( 20, 0, false );drive1.plugIn( );drive1.formatDrive( );drive1.writeData( 5 );drive1.pullOut( );drive2.plugIn( );drive2.formatDrive( );drive2.writeData( 1 );drive2.pullOut( );cs52::FlashDrive combined = drive1 + drive2;cout &lt;&lt; “this drive’s filled to ” &lt;&lt; combined.getUsed( ) &lt;&lt; endl;cs52::FlashDrive other = combined – drive1;cout &lt;&lt; “the other cup’s filled to ” &lt;&lt; other.getUsed( ) &lt;&lt; endl;if (combined &gt; other) {cout &lt;&lt; “looks like combined is bigger…” &lt;&lt; endl;}else {cout &lt;&lt; “looks like other is bigger…” &lt;&lt; endl;}if (drive2 &gt; other) {cout &lt;&lt; “looks like drive2 is bigger…” &lt;&lt; endl;}else {cout &lt;&lt; “looks like other is bigger…” &lt;&lt; endl;}if (drive2 &lt; drive1) {cout &lt;&lt; “looks like drive2 is smaller…” &lt;&lt; endl;}else {cout &lt;&lt; “looks like drive1 is smaller…” &lt;&lt; endl;}}</td>

  </tr>

 </tbody>

 <tbody>

  <tr>

   <td width="37%">int my_StorageCapacity;int my_StorageUsed;bool my_IsPluggedIn;</td>

  </tr>

  <tr>

   <td colspan="2" rowspan="2" width="38%"></td>

  </tr>

 </tbody>

 <tbody>

  <tr>

   <td width="62%"></td>

  </tr>

 </tbody>

</table>




<table border="1" width="29%" cellspacing="0" cellpadding="0">

 <tbody>

  <tr>

   <td width="15%"><img decoding="async" width="105" height="72" align="bottom" data-recalc-dims="1" data-src="https://i0.wp.com/www.howardstahl.com/cs52/flash1.jpg?resize=105%2C72" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

    <noscript>

     <img decoding="async" src="https://i0.wp.com/www.howardstahl.com/cs52/flash1.jpg?resize=105%2C72" width="105" height="72" align="bottom" data-recalc-dims="1">

    </noscript></td>

   <td width="11%"><img decoding="async" width="87" height="100" align="bottom" data-recalc-dims="1" data-src="https://i0.wp.com/www.howardstahl.com/cs52/flash2.jpg?resize=87%2C100" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

    <noscript>

     <img decoding="async" src="https://i0.wp.com/www.howardstahl.com/cs52/flash2.jpg?resize=87%2C100" width="87" height="100" align="bottom" data-recalc-dims="1">

    </noscript></td>

  </tr>

 </tbody>

</table>

<h3><strong>Overall</strong></h3>

<ul>

 <li>Your submission should follow this organization:

  <ul>

   <li>part_a

    <ul>

     <li>main.cpp</li>

     <li>flashdrive_2_0.h</li>

     <li>flashdrive_2_0.cpp</li>

    </ul></li>

  </ul></li>

</ul>