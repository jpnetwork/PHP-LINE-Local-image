<?php
$token = "YOUR_LINE_TOKEN" ; // LINE Token
//Message
$mymessage = "เรื่อง: ทดสอบส่งข้อความ \n"; //Set new line with '\n'
$mymessage .= "จาก: ข้อความจากแมว \n";
$mymessage .= "รายละเอียด: แมวหิวแล้วจ้า";
$imageFile = new CURLFILE('cat.jpg'); // Local Image file Path
$sticker_package_id = '2';  // Package ID sticker
$sticker_id = '34';    // ID sticker
  $data = array (
    'message' => $mymessage,
    'imageFile' => $imageFile,
    'stickerPackageId' => $sticker_package_id,
    'stickerId' => $sticker_id
  );
  $chOne = curl_init();
  curl_setopt( $chOne, CURLOPT_URL, "https://notify-api.line.me/api/notify");
  curl_setopt( $chOne, CURLOPT_SSL_VERIFYHOST, 0);
  curl_setopt( $chOne, CURLOPT_SSL_VERIFYPEER, 0);
  curl_setopt( $chOne, CURLOPT_POST, 1);
  curl_setopt( $chOne, CURLOPT_POSTFIELDS, $data);
  curl_setopt( $chOne, CURLOPT_FOLLOWLOCATION, 1);
  $headers = array( 'Method: POST', 'Content-type: multipart/form-data', 'Authorization: Bearer '.$token, );
  curl_setopt($chOne, CURLOPT_HTTPHEADER, $headers);
  curl_setopt( $chOne, CURLOPT_RETURNTRANSFER, 1);
  $result = curl_exec( $chOne );
  //Check error
  if(curl_error($chOne)) { echo 'error:' . curl_error($chOne); }
  else { $result_ = json_decode($result, true);
  echo "status : ".$result_['status']; echo "message : ". $result_['message']; 
  }
  //Close connection
  curl_close( $chOne );
