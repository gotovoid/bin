#!/bin/bash

input=${1:?input is empty}

cat <<"_EOF_"
<html>
<head>
<meta charset="utf-8">
<title>reflesh every 2000 msec</title>
</head>
<body onload='javascript: setTimeout("location.reload(true);", 2000);'>
_EOF_

markdown $input

cat <<"_EOF_"
</body>
</html>
_EOF_
