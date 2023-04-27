# GSheetToHtml-Sundeep
Worked like a charm
Start with this, to get data , not put data. Tested ok. https://b.codewithsundeep.com/2022/08/google-sheet-to-json.html

Create API endpoint as mentioned here - https://b.codewithsundeep.com/2022/05/html-form-to-google-sheet.html

shared sheet: https://docs.google.com/spreadsheets/d/1V3yJNLWNhsnDXOXkoOxMxYX9FeYCnt0LWMZMdabtnTg/edit?usp=sharing

codes in the .gs
const ss = SpreadsheetApp.openByUrl("https://docs.google.com/spreadsheets/d/1V3yJNLWNhsnDXOXkoOxMxYX9FeYCnt0LWMZMdabtnTg/edit?usp=sharing")
const sheet = ss.getSheetByName("Sheet1")
function doGet(e){
  let obj = {};
  let data = sheet.getDataRange().getValues()
  obj.content = data;
return ContentService.createTextOutput(JSON.stringify(obj)).setMimeType(ContentService.MimeType.JSON)
}

new deployment, webapp, copy the api endpoint.
