
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
