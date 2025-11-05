## Username
natas11

## Password
UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk

## Write-Up
'''
// Finding Key Process
// A^Key=B -> A^B=Key
<?php
$cookie='HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg%3D';
function xor_encrypt($in) {
    $default_data = '{"showpassword":"no","bgcolor":"#ffffff"}';
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $default_data[$i];
    }

    return $outText;
}
//Decoding Base64
$decoded_base64=base64_decode($cookie);
print(xor_encrypt($decoded_base64));
'''

## Method of solve
