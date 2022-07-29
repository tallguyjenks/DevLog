
- [[s.q.tsql]] [[SSIS|ssis]]
  - Can use variables within visual elements
  - Can call scripts and other files like [[C|s.l.clang]]
  - Can run processes in loops and have automation steps that send email reports
- [[s.m.html]]
  - Using [[@Andy Matuschak|@andy-matuschak]]'s Mnemonic Medium we can make web pages that add items to your "[Orbit](https://withorbit.com/)" | [Orbit Code](https://github.com/andymatuschak/orbit) \| [Orbit Docs](https://docs.withorbit.com/)
  - These components are driven by [[JavaScript]] embedded into [[HTML 1]] web pages with this code:
  	  ```html
  	  			  <!DOCTYPE HTML>
  	  			  <html>
  	  			    <head>
  	  			      <script type="module" src="https://js.withorbit.com/orbit-web-component.js"></script>
  	  			    </head>
  	  			    <body>
  	  			      <orbit-reviewarea color="brown">
  	  			        <orbit-prompt
  	  			          question="What's the working name for Andy's experimental mnemonic medium platform?"
  	  			          answer="Orbit"
  	  			        ></orbit-prompt>
  	  			        <orbit-prompt
  	  			          question="What's the new-ish web technology used to embed Orbit prompts into web pages?"
  	  			          answer="Web components"
  	  			        ></orbit-prompt>
  	  			        <orbit-prompt
  	  			          question="Given a right triangle with legs of length $a$ and $b$, what is the length of hypotenuse $c$?"
  	  			          answer="$$c = \sqrt{a^2 + b^2}$$"
  	  			        ></orbit-prompt>
  	  			      </orbit-reviewarea>
  	  			    </body>
  	  			  </html>
  	  			  ```
  	-
  ```

