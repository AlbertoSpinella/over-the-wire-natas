Over the Wire's **Natas** Walkthrough by AlbertoSpinella.

Don't be sly! Try to solve the challenges on your own before comparing with my solutions.

# Index
1. natas 0
2. natas 0 -> 1
3. natas 1 -> 2
4. natas 2 -> 3
5. natas 3 -> 4
6. natas 4 -> 5

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
