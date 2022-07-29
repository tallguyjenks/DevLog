
## Metadata

<https://youtu.be/I08syTslan8>

---

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/I08syTslan8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></center>

---

## Notes

- [[terms.idempotent]] [[terms.api]]'s should not duplicate an outcome despite duplicating requests
  - should a server not respond to a request then if we send more requests the outcome should not result in multiple events or side effects
- Resilient [[terms.api]]'s use built-in client retries, client generated tokens to guarantee [[terms.idempotent]]cy, and return identical responses to support predictable client behavior
- Approaches
  - ![attempt1](/assets/images/2022-02-24-13-36-48.png)
    - Client makes request
    - [[terms.api]] Arguments are sent to the Resource server
    - A hash function on the arguments is generated and creates a request token
    - The request token is then stored in a stateStore database in the resource server
    - The resources server then fulfills the request
    - If a duplicate request is sent, the first thing that happens is the stateStore is checked for this request and if it has already been fulfilled then it can kick back an error response and not crash.
      - The token's uniqueness could be the hash, on several items, the timestamp, the user, the actual request content, and several other things to make it easily unique
        - downside is, what if we actually WANTED to have multiple requests granted?
  - ![A better way](/assets/images/2022-02-24-13-50-53.png)
    - Instead of resource server inspecting the resource arguments to determine if this is a repeat request or a duplicate, or retry we put the onus on the Client
    - as part of the [[terms.api]] contract, you (the user) need to provide a [[terms.uuid]] as part of sending a request
    - this way the token from the client sent to the resource server is either duplicated for a retry or a duplicate action and can get processed or kicked back if appropriate
    - but if the client sends a duplicate request but with a different [[terms.uuid]] then the resources server can check the state store and determine that multiple requests need to be fulfilled.
    - Important point is that for any requests that use the same token, the resource server but return syntactically identical responses
      - Why is this important?
        - ![Always Success](/assets/images/2022-02-24-13-58-19.png)
        - What if our first request made it through and our request was fulfilled, and we never got a response of success back
        - We then send a retry which is now a duplicate request in the stateStore.
        - Do we send an error message back that a duplicate operation is occurring?
        - No, we should just send a `Success` response back for the duplicate request because the request has already been fulfilled so ultimately the duplicate is trying to do something that was already done so in this case the user receives success
