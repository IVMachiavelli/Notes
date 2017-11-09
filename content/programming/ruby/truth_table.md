---
title: "Truth Table"
draft: false
---

{{% panel="Truth Table" header="Ruby Truth Table" theme="default" %}}

<h3>NOT true?</h3>
!false 	true<br>
!true 	false<br>

<h3>OR (||) true?</h3>
true || false 	true<br>
true || true 	true<br>
false || true 	true<br>
false || false 	false<br>

<h3>AND (&&) true?</h3>
true && false 	false<br>
true && true 	true<br>
false && true 	false<br>
false && false 	false<br>

<h3>NOT OR 	true?</h3>
not (true || false) 	false<br>
not (true || true) 	false<br>
not (false || true) 	false<br>
not (false || false) 	true<br>

<h3>NOT AND 	true?</h3>
!(true && false) 	true<br>
!(true && true) 	false<br>
!(false && true) 	true<br>
!(false && false) 	true<br>

<h3>!= 	true?</h3>
1 != 0 	true<br>
1 != 1 	false<br>
0 != 1 	true<br>
0 != 0 	false<br>

<h3>== 	true?</h3>
1 == 0 	false<br>
1 == 1 	true<br>
0 == 1 	false<br>
0 == 0 	true<br>
