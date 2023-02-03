<!doctype html>
<html lang="en">

  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet"
	  integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

    <title>WebRTC PeerJs Demo</title>
  </head>

  <body>
    <!-- As a heading -->
    <nav class="navbar navbar-light bg-dark">
	  <div class="container-fluid">
		<span class="navbar-brand mb-0 h1" style="color: aliceblue;">WebRTC PeerJs Demo</span>
	  </div>
    </nav>
    <div class="container-fluid">


	  <div class="row">
		<div class="col-5 pt-5 ps-5 col-sm-7">
		  <label class="form-label">Enter Room ID to connect or create</label>
		  <input id="room-input" type="text" class="form-control" placeholder="room ID">
		  <br>
		  <div class="col-auto">
			<button type="submit" class="btn btn-secondary mb-3" onclick="createRoom()">Create Room</button>
			<button type="submit" class="btn btn-primary mb-3" onclick="joinRoom()">Join Room</button>
			<button type="submit" class="btn btn-success mb-3" onclick="joinRoomWithoutCamShareScreen()">Join
			  Room and Share screen directly</button>
			<button type="submit" class="btn btn-dark mb-3" onclick="joinRoomShareVideoAsStream()">Join
			  Room and stream local media </button>
		  </div>
		</div>
		<div class="col-7 pt-5 ps-5 pe-5 col-sm-5">
		  <div class="alert alert-info alert-dismissible fade show mt-3" role="alert" id="notification" hidden>
			<strong>Holy guacamole!</strong> You should check in on some of those fields below.
			<button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
		  </div>
		</div>
	  </div>
	  <div class="row">
		<div class="col ps-5 pt-5" id="local-vid-container" hidden>
		  <div class="row">
			<div class="col">
			  <h2>Local Stream</h2>
			</div>

		  </div>
		  <div class="row p-3">
			<video height="300" id="local-video" controls class="local-video"></video>
		  </div>
		  <div class="row">
			<div class="col-3 col-sm-12"><button type="submit" class="btn btn-success mb-3"
				onclick="startScreenShare()">Share Screen</button>
			</div>
		  </div>
		</div>
		<div class="col ps-5 pt-5" id="screenshare-container" hidden>
		  <div class="row">
			<div class="col">
			  <h2>Screen Shared Stream</h2>
			</div>

		  </div>
		  <div class="row p-3">
			<video height="300" id="screenshared-video" controls class="local-video"></video>
		  </div>
		  <!-- <div class="row">
		  <div class="col-3 col-sm-12"><button type="submit" class="btn btn-success mb-3"
		  onclick="startScreenShare()">Share Screen</button>
		  </div>
		  </div> -->
		</div>
		<div class="col ps-5 pt-5" id="remote-vid-container" hidden>
		  <div class="row">
			<div class="col">
			  <h2>Remote Stream</h2>
			</div>

		  </div>
		  <div class="row p-3">
			<video height="300" id="remote-video" controls class="remote-video"></video>
		  </div>
		</div>

		<div class="col ps-5 pt-5" id="local-mdeia-container" hidden>
		  <div class="row">

			<div class="col">
			  <h2>Local video from media</h2>
			  <h6>On play stream to remote peer</h6>
			</div>
		  </div>
		  <div class="row p-3">
			<video height="300" id="local-media" controls muted loop
			  src="/im.abhishekbhardwaj bharmour.mp4"></video>
		  </div>
		</div>
	  </div>

    </div>

    <!-- Optional JavaScript; choose one of the two! -->

    <!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
	  integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
	  crossorigin="anonymous"></script>


    <!-- check https://peerjs.com/ for latest CDN-->
    <script src="https://unpkg.com/peerjs@1.4.7/dist/peerjs.min.js"></script>
    <script src="js/script.js"></script>
  </body>

</html>
