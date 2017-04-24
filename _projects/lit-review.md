---
layout: project
comments: true

title: Literature View On Game Based Object Oriented Teaching

introduction: This is a review on studies based on game based teaching strategies for object oriented teaching.
---
<object data="/data/projects/literature_review.pdf"
        type="application/pdf" width="100%" height="200%">
    <iframe src="/data/projects/literature_review.pdf#page=1" 
            width="100%" height="200%" style="border: none;">            
    This browser does not support PDFs. Please download the PDF to view it:
    <a href="/data/projects/literature_review.pdf">Download Literature Review</a>
</iframe>
</object>

<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js"></script>
<script src="http://ajax.aspnetcdn.com/ajax/jquery.ui/1.8.9/jquery-ui.js" type="text/javascript"></script>
<link href="http://ajax.aspnetcdn.com/ajax/jquery.ui/1.8.9/themes/blitzer/jquery-ui.css" rel="stylesheet" type="text/css" />
<script type="text/javascript">
    $(function () {
        var fileName = "/data/projects/literature_review.pdf";
        $("#btnShow").click(function () {
            $("#dialog").dialog({
                modal: true,
                title: fileName,
                width: 540,
                height: 450,
               
                open: function () {
                    var object = "<object data=\"{FileName}\"
                                          type=\"application/pdf\"
                                          width=\"500px\" height=\"300px\">";
                    object += "If you are unable to view file, 
                               you can download from 
                               <a href = \"{FileName}\">here</a>";             
                    object += " or download 
                                <a target = \"_blank\" href =
                                \"http://get.adobe.com/reader/\">
                                Adobe PDF Reader</a> to view the file.";
                    object += "</object>";
                    object = object.replace(/{FileName}/g, "Files/" +
                                            fileName);
                    $("#dialog").html(object);
                }
            });
        });
    });
</script>
<input id="btnShow" type="button" value="Show PDF" />
<div id="dialog" style="display: none">
</div>