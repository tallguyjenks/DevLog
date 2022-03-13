---
id: 6txd4hqbngr26pnnat4z3he
title: 106 Extract Function
desc: ''
updated: 1642625949497
created: 1641105063874
stub: false
isDir: false
---

```javascript
// FROM
function printOwing(invoice) {
	printBanner();
	let outstanding = calculateOutstanding();

	//print details
	console.log(`name: ${invoice.customer}`);
	console.log(`amount: ${outstanding}`);
}

// TO
function printOwing(invoice) {
	printBanner();
	let outstanding = calculateOutstanding();
	printDetails(outstanding);

	function printDetails(outstanding) {
		console.log(`name: ${invoice.customer}`);
		console.log(`amount: ${outstanding}`);
	}
}
```
