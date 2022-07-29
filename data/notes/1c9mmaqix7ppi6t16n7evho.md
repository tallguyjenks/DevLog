
- [[s.l.bash]] `case` statements can have actions split legibly across lines for legibility

```bash
case "$RESPONSE" in
	[QqNn]) 
	Clean_Exit
	;;
	[Yy])
	git config --global user.name "$USER_NAME"
	git config --global user.email "$USER_EMAIL@covered.ca.gov"
	echo -e "\n${GREEN}Great!${NC} That's all configured now...$successful_execution_msg"
	;;
	*)
	>&2 echo -e "Invalid choice, please select either ${LGREEN}y${NC} or ${LRED}n${NC}\n\n"
	sleep 1
	Dirty_Exit
	;;
esac
```

- [[s.l.bash]] using git bash you can open a windows explorer window in the current directory by running the command `explorer`
-  [[s.l.rust]] [[s.l.python]] [Google's Dependency Management service](https://deps.dev/)
  

