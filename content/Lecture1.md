Title: Lecture1 Details
Date: 2019-07-23 23:39
Modified: 2019-05-07 23:39
Category:Moduel 1

#Topic Name: Representing Text and Language

#<li><a href="https://drive.google.com/file/d/1fvQnvDf2hBbgrgUieRytHlAL2getXDtb/view?usp=sharing" target="_blank">Pre-Reading</a></li> <br>

#Slides<br>
#<li><a href="https://www.dropbox.com/home/Batch7/Slides/Day04?preview=1-Representing_Text_and_Language.pptx" target="_blank">Representing Text and Language
</a></li> <br>



#Preview Video <br><br>
<iframe src="https://videoken.com/embed/vkene-a0yjEjEBKw"width="640" height="480"></iframe>

#Experiment<br><br>
**BOW_20newsgroup** <br>
1.  Representation of  text document using Bag of Words<br>
2.  Understand Bag of Words represented text data with K-nearest neighbours<br>

**Note:**Here is the following Notebook For [BOW_20newsgroup](https://drive.google.com/file/d/1r_W2Dz442PlDXM-qBpsVoW6SR3KPxDga/view?usp=sharing)

<br><br>

###Experiment Explanation Video <br><br>
<iframe src="https://cdn.talentsprint.com/aiml/AIML_BATCH_HYD_7/Week_1/bag_of_words.mp4"width="640" height="480"></iframe>

<br><br>

#Lecture Video (Batch 9) <br><br>
<iframe src="https://videoken.com/embed/vkene-dPokq_0Irg"width="640" height="480"></iframe>



<style>

html{
     width : 100%;
     height: 100%;
}

body{
     width : 100%;
     height: 100%;
}

.comentBox{
     padding:1%
     width : 96%;
     border: 1px solid #000;
     background-color: #00FFFF;
     margin-bottom:10px;
     text-align : center;
}

.leftPanelImg{
     width: 10%;
     float : left;

}
.leftPanelImg img{
     border-radius:20px;
}
.Rightpanel{
     width: 85%;
     float: left;
     margin-left:1%;

}
.clear{
      clear :both;
}
.comentBox h5{
     text-align : center;

}
.comentBox input[type ="text"], .comentBox input[type ="date"],.comentBox textarea{
     border:1px solid #000;
     padding:2px;
     width: 300px;
}



</style>
<body>
<div class = 'comentBox'>
	<form id="form">	
        <h5> Add Comment </h5>
       Name: <input type = "text" id ="firstname" required><br/><br/>
       Date: <input type = "date" id ="date" required><br/><br/>
       Body: <textarea rows ="5" col ="30" id ="body" required></textarea><br/><br/>
       <input type = "submit" id ="addcoment" value ="Add Comment"/>
        </form>
</div>


<div id ='container'></div>
<script src = "https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.4/jquery.js"></script>
<script>

	let itemsArray = localStorage.getItem('items') ? JSON.parse(localStorage.getItem('items')) : [];
       //localStorage.clear()

	const data = JSON.parse(localStorage.getItem('items')); 

	const render = (data) => {
	  const html = "<div class = 'comentBox'><div class ='leftPanelImg'><img src = 'images/AI-7.jpg'width='200' height= '121'></div> <div class ='Rightpanel'><span>"+data.firstname+"</span><div class = 'date'>"+data.date+"</div><p>"+data.body+"</p></div><div class ='clear'></div></div>";
	 $("#container").append(html);
	}

	$( "#form" ).submit(function (e) {
	  e.preventDefault();

	  		const addObj ={
                    "firstname": $('#firstname').val(),
                    "date" : $('#date').val(),
                    "body": $('#body').val(),
          };
	  itemsArray.push(addObj);
	  localStorage.setItem('items', JSON.stringify(itemsArray));
         
	  $("#firstname, #date, #body").val('');

	  render(addObj);
	});

	data.forEach(item => {
	  render(item);
	});
</script>
</body>






