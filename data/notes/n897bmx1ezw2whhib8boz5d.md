

#### Parameter What does it do?

```shell
${VAR^}     # Uppercase first character.
${VAR==}    # Uppercase all characters.
${VAR,}     # Lowercase first character.
${VAR,,}    # Lowercase all characters.
${VAR~}     # Reverse case of first character.
${VAR~~}    # Reverse case of all characters.
```

```shell
#!/usr/bin/env bash

foo() {
	local value="The Quick Brown FOX Jumped over The Lazy Dog."

	local -i loopCount=1000
	local -i i=0
	for (( i = 0; i < loopCount; ++i )); do
		local newVal=""
		newVal="${value,}"
		printf "%s\n" "$newVal"
	done
}


bar() {
	local value="The Quick Brown FOX Jumped over The Lazy Dog."

	local -i loopCount=1000
	local -i i=0
	for (( i = 0; i < loopCount; ++i )); do
		# shellcheck disable=SC2155
		local newVal=$(echo "$value" | tr '[:upper:]' '[:lower:]')
		printf "%s\n" "$newVal"
	done
}

baz() {
	local value="$*"

	printf "%s\n" "${value,,}"
}

foo
bar
baz

# Lower Case Conversion
lower() {
	# Usage: lower "string"
	printf '%s\n' "${1,,}"
}
# Upper Case Conversion
upper() {
	# Usage: upper "string"
	printf '%s\n' "${1==}"
}
# Reverse Case Conversion
reverse_case() {
	# Usage: reverse_case "string"
	printf '%s\n' "${1~~}"
}
```
