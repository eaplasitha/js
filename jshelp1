



function post2(path, token) {
			
			var http = new XMLHttpRequest();
			var url = path;
			alert("token" + token);
			//params = getParemList(params);
			http.open("POST", url, true);

			//Send the proper header information along with the request
			http.setRequestHeader("Content-type", "application/json");
			http.setRequestHeader("Authorization", "Bearer " + token);
			//http.setRequestHeader("Content-length", params.length);
			//http.setRequestHeader("Connection", "close");

			http.onreadystatechange = function() {//Call a function when the state changes.
			    if(http.readyState == 4 && http.status == 200) {
			        alert("resalt1" + http.responseText);
			    }
			    //alert("resalt2" + http.responseText);
			    var jsonResponse = JSON.parse(http.responseText);
			    var ltiparameters=jsonResponse['parameter'];
			    var ltiurl=jsonResponse['url'];
			    var ltiaction= ltiurl + "?";
			    var isstart=1;
				for(var key in ltiparameters) {
			    	if(isstart==0){
			    		ltiaction=ltiaction+"&";
			    	}
			    	ltiaction = ltiaction+ltiparameters[key].key +"="+  ltiparameters[key].value;
			    	isstart=0;
			    }
			    alert("ltiaction: " +ltiaction);
			    var form=document.getElementById("ltiForm");
				form.setAttribute("method","POST");
				form.setAttribute("action",ltiaction);
				form.submit();
			}

			http.send('{"consumer":"REVEL", "context_id":"545816ade4b0cc09b4de4a0f", "custom_assignment_end_date":"2014-11-27T23:00:00.000Z", "custom_mode":"" ,"resource_link_id":"3382bee1-1fb8-45ef-af03-ec8c67456673" , "resource_link_title":"This_is_provided_by_Revel" , "tool_consumer_instance_description":"REVEL" , "custom_course_time_zone":"","launch_presentation_locale":"en-US","provider":"writingspace","profile":"assignment1.0"}');
		}
