

## javascript/Examples

# 1.Ajax Examples

```
function getReportByCategory(that){    
            var sub_category = $.trim(that.val());
            var report_list = that.parent().parent().parent().find('.sortedData');
            var select_year = that.parent().parent().find('.select_year');
            select_year.fadeIn();

            if(sub_category != '' ){
               $.ajax({
                  url: 'base_url/getReport.php',
                  type: 'post',
                  dataType: 'json',
                  data: {'sub_category':sub_category,'type':'category'},
                  //contentType: 'application/json',
                cache: false,
                contentType: false,
                processData: false,
                   beforeSend: function() {
                    // $("#formLoader").show();
                },
                  success: function (data) {

//                   var res = JSON.parse(data);
  //                  console.log(res);

                     var report_html = '';
                     year_html = "<option value=''>All Years</option>";

                     if(data.all_reports.length == 0){
                        report_html = "<p>Please select the period</p>";
                     }else{
                        $.each(data.all_reports, function(index, item) {
                           /*report_html += '<div class="pdfBlock">';
                           report_html += '<p><a href="base_url/uploads/'+item.report_path+'" download>'+item.title+'</a></p>';
                           report_html += '</div>';*/

                           report_html += '<a href="base_url"'+item.report_path+'" target="_blank" rel="noopener noreferrer"><div class="pdfBlock"><p>'+item.title+'</p></div></a>';
                        });
                     }

                     if(data.years.length == 0){
                        year_html = "<option value=''>No year</option>";
                        select_year.fadeOut();
                     }else{
                        $.each(data.years, function(index, item) {
                           year_html += "<option value='"+item.id+"'>"+item.year_name+"</option>";
                        });
                     }
                     report_list.html(report_html);      
                     select_year.html(year_html);                       
                  }, error: function(error) {
                    console.log("Error fetching data: " + error);
                }
               });
            }
```

# 2. Image Validation Client side.

```
<script>
    function checkWebPImage(field_id, file, maxSizeKB) {
        // console.log(event.value);
        console.log(file.type);
        let fileInput = document.getElementById(field_id);
        // Define the maximum allowed size in kilobytes
        maxSizeKB = maxSizeKB || 1024;

        // Check if the file is an image based on the MIME type
        if (file.type.startsWith('image/')) {
            // Check if the file size is within the allowed limit
            if (file.size <= maxSizeKB * 1024) {
                // if (file.type != "image/webp") {
                //     alert('File is not a WebP image.');
                //     fileInput.value = '';
                //     return false;
                // }
                // Read the first few bytes of the file to check the header

                const reader = new FileReader();

                reader.onload = function(e) {
                    const imageUrl = e.target.result;
                    console.log(imageUrl);

                };

                reader.readAsArrayBuffer(file);


            } else {
                alert(`Current File Size ${formatFileSize(file.size)} File size exceeds the allowed limit`);
                fileInput.value = '';
                return false;

            }
        } else {
            alert('File is not an image !!.');
            fileInput.value = '';
            return false;

        }
    }

    document.getElementById('profile_img').addEventListener('change', function(event) {
        let file = event.target.files[0];
        let field_id = 'profile_img';
        checkWebPImage(field_id, file, 500); // Check for a WebP image with a maximum size of 500 KB
    });
</script>
```

# 3 Jquery

```
$('.pro_logo').attr('src', prj.logo_image);  // image update
$('.dyn_reg_no').text(prj.rera_no); // p,span,div 
$('.dyn_contact_email').attr('href', 'mailto:' + prj.contact_email);  // email tag
$('.dync_payment_plans').html(' '); // empty html

 # Fire Event  
$(document).on('change', '#project_name', function(e) {
            let sel_pid = $(this).val();
});

on page load
 $(document).ready(function() {
});

Checked for checkbox
 var is_agreed= $('#iAgreeTerms').prop('checked');

```

### shortcut to capture form data

```

var form = document.getElementById('onlineApplicationForm'); //  form id
            var formData = new FormData(form); // return all form value

setTimeout(() => {
                    function_name(city);
                }, 1000);
```

### nodejs version switch steps [https://codedamn.com/news/nodejs/nvm-installation-setup-guide]

