p.534
if문 아래부터


```
if (resource.exists() == false) {

return  new ResponseEntity<>(HttpStatus.NOTFOUND);

}

String resourceName = resource.getFilename();

HttpHeaders headers = new HttpHeaders();

try {

String downloadName = null;

if(userAgent.contains("Trident")) {

log.info("IE browser");

downloadName = URLEncoder.encode(resourceName,"UTF-8").replaceAll("\\+", " ");

}else  if(userAgent.contains("Edge")) {

log.info("Edge browser");

downloadName =  URLEncoder.encode(resourceName,"UTF-8");

log.info("Edge name: " + downloadName);

}else {

log.info("Chrome browser");

downloadName = new String(resourceName.getBytes("UTF-8"), "ISO-8859-1");

}

headers.add("Content-Disposition", "attachment; filename=" + downloadName);

} catch (UnsupportedEncodingException e) {

e.printStackTrace();

}

return  new ResponseEntity<Resource>(resource, headers, HttpStatus.OK);

}

```


p. 591 
if 문 아래 오탈자

```
if (modifyResult && board.getAttachList() != null && board.getAttachList().size() > 0) {```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYwNjczNTY3NywxMjkzODY3NTM4XX0=
-->