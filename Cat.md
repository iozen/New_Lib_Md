**cat from ls**

cat $(ls) | grep "err"
cat $(ls) | grep "ше шось") | grep "err"

**cat from locate**

cat $(locate validation.php) | grep "err"
cat $(locate validation.php | grep "ше шось") | grep "err"