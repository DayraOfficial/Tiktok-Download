<?php
include "DownloadClass.php";

$api = new DownloadClass();

// https://vt.tiktok.com/ZSe1Xp5Y3/

$error = false;
$errorMsg = "";
$strCon = false;
$str = '';

if(isset($_POST["buttonData"])) {
  $input = $_POST["input"];
  
  if($input != "") {
    if(filter_var($input, FILTER_VALIDATE_URL)) {
      
      $result = $api->Data($input);
      $resultErr = $result["err"];
      
      if($resultErr == "false") {
        $strCon = true;
        $str = '<div class="row justify-content-center mt-5 bg-primary rounded-3 p-3" id="detailContent">
      <h3 class="text-center my-3">Data Video Tiktok</h3>
      <div class="col-md-5">
        ' . $result["embedVid"] . '
      </div>
      <div class="col-md-2">
        
      </div>
      <div class="col-md-5">
        <div class="d-flex justify-content-center">
          <img src="' . $result["imageUrl"] . '" width="100" class="rounded-circle img-thumbnail mb-2">
        </div>
        
        <div class="text-center fs-5">
          <p> <b>Title :</b> '. $result["title"] .'</p>
          <p> <b>Nickname :</b> '. $result["nickname"] .'</p>
          <p> <b>Nick Id :</b> @'.  $result["nickId"] .'</p>
        </div>
      </div>
      
      <div class="col-md-8 mt-3">
        <form method="post">
            <input type="hidden" value="' . $result["filename"] . '" name="filename">
            <input type="hidden" value="' . $result["playAddr"] . '" name="url">
          <div class="d-grid gap-2">
            <button type="submit" class="btn btn-info" name="buttonDownload" id="buttonDownload">
              <i class="bi bi-download"></i> Download Video
            </button>
          </div>
        </form>
      </div>
      
    </div>';
        
      } else {
        $error = true;
        $errorMsg = $result["message"];
      }
      
    } else {
      $error = true;
      $errorMsg = "Input Field Must Be Url";
    }
    
  } else {
    $error = true;
    $errorMsg = "Input Field Must Be Required";
  }
  
}

if(isset($_POST["buttonDownload"])) {
  $url = $_POST["url"];
  $filename = $_POST["filename"];
  
  $api->DownloadUrl($url, $filename);
}

?>

