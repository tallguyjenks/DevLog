

## Async and Defer

<center>
	<iframe width="560" height="315" src="https://www.youtube.com/embed/BMuFBYw91UQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

Normal DOC parsing is that is parses synchronously, so as soon as it hits a `<script>` tag it stops and downloads that content first and then executes it and only THEN continues with the HTML download/parsing.
