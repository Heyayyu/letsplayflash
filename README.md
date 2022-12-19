# letsplayflash
<!DOCTYPE html>
<html>
<head>
  <title>'Bout Blank 'Bedder</title>
  <script>
  var win
//thing for aboutblank
function aboutblank(url){
    win = window.open(); 
  win.document.body.style.margin = "0"; 
  win.document.body.style.height = "100vh";
  var iframe = win.document.createElement("iframe"); 
  iframe.style.border = "none"; 
  iframe.style.width = "100%"; 
  iframe.style.height = "100%"; 
  iframe.style.margin = "0";
  iframe.referrerpolicy = "no-referrer"; 
  iframe.allow = "fullscreen"; 
  iframe.src = url; win.document.body.appendChild(iframe);
}

//change title and favicon of new tab
function changefat(doc, title, image){
    doc.title=title;
  var icon=doc.querySelector(`link[rel='icon']`);
  if (!icon) {
    icon = doc.createElement('link');
    icon.rel='icon';
    icon.setAttribute("href",image);
    doc.head.appendChild(icon);
    }
}

function start(){
    aboutblank(document.getElementById("url").value);
  if (document.getElementById("check").value){
      changefat(win.document, document.getElementById("title").value, document.getElementById("image").value);
  }
}
  </script>
</head>
<body>
  <h1>'Bout Blank 'Bedder</h1>
  <form onsubmit="event.preventDefault();start();">
  <label for="url">The URL you want to open:</label>
  <input type="url" placeholder="Type Link Here" id="url"> 
  <br>
  <label for="check">Mask?</label>
  <input type="checkbox" id="check" checked>
  <br>
  <label for="title">Title of tab:</label>
  <input type="text" placeholder="Type Title Here" id="title" value="My Drive - Google Drive"> 
  <br>
  <label for="image">The URL of the image you want to use:</label>
  <input type="text" placeholder="Type Link Here" id="image" value="https://ssl.gstatic.com/docs/doclist/images/drive_2022q3_32dp.png"> 
  <br>
  <input type="submit" value="Open">
  <input type="reset"> 
  </form>
</body>
</html>
