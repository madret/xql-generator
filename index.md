<html>

var survey_options = document.getElementById('survey_options');
var add_more_fields = document.getElementById('add_more_fields');
var remove_fields = document.getElementById('remove_fields');

add_more_fields.onclick = function(){
  var newField = document.createElement('input');
  newField.setAttribute('type','text');
  newField.setAttribute('name','survey_options[]');
  newField.setAttribute('class','survey_options');
  newField.setAttribute('siz',50);
  newField.setAttribute('placeholder','Another Field');
  survey_options.appendChild(newField);
}

remove_fields.onclick = function(){
  var input_tags = survey_options.getElementsByTagName('input');
  if(input_tags.length > 2) {
    survey_options.removeChild(input_tags[(input_tags.length) - 1]);
  }
}

<head>
  <title>Dynamic Fields - Day #29</title>
  <link rel="stylesheet" type="text/css" href="style.css">
  <!-- include font awesome -->
    <link rel="stylesheet" type="text/css" href="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">

</head>
<body>

  <h1>Dynamic Fields Javascript</h1>
  <div class="wrapper">
    <div id="survey_options">
      <input type="text" name="survey_options[]" class="survey_options" size="50" placeholder="Name">
      <input type="text" name="survey_options[]" class="survey_options" size="50" placeholder="Email">
      <input type="text" name="survey_options[]" class="survey_options" size="50" placeholder="Another Field">
    </div>
    <div class="controls">
      <a href="#" id="add_more_fields"><i class="fa fa-plus"></i>Add More</a>
      <a href="#" id="remove_fields"><i class="fa fa-plus"></i>Remove Field</a>
    </div>
  </div>
<script src="script.js"></script>
</body>
</html>
