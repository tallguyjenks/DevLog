---
id: su0vmv0rlvwjrxyogt7xgue
title: 272 Replace Conditional with Polymorphism
desc: ''
updated: 1642626832366
created: 1641105063875
stub: false
isDir: false
---

```javascript
//FROM
switch (bird.type) {
    case 'EuropeanSwallow':
        return "average";
    case 'AfricanSwallow':
        return (bird.numberOfCoconuts > 2) ? "tired" : "average";
    case 'NorwegianBlueParrot':
        return (bird.voltage > 100) ? "scorched" : "beautiful";
    default:
        return "unknown";
}

//TO
class EuropeanSwallow {
    get plumage() {
        return "average";
    }}
class AfricanSwallow {
    get plumage() {
        return (this.numberOfCoconuts > 2) ? "tired" : "average";
    }
)
class NorwegianBlueParrot {
    get plumage() {
        return (this.voltage > 100) ? "scorched" : "beautiful";
    }
}
```
