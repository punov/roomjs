# RoomJS
The simplest and most convenient way to create 3D experience for your website!
Do you have simple, dumb and plane HTML templates?
Add `<script src="room.js"></script>` to your website,
and obvious 20-30 lines of code will create fantastic WOOOW effect for your users!

> Hey, mom! I can create 3d-website by simple HTML and few lines of javascript code.
> Oh, my Godness!

Lets imagine, that you have your old website with stupid old template pages like:
about.html, gallery.html, etc.

Look onto this snapshot:
```javascript
var room = Room.create('images/PhotoOfMyRoom/');
room.placeTemplate('about.html', {});
room.placeTemplate('gallery.html', {});
room.placeTemplate('contact.html', {});
```

That's it! Now you have a 3D-room full of your markups.
You can upload photos of your room, or any area/place/basement,
you just need to take 6 photos, its pretty `<a>easy</a>`,
or use photos of famous places from `<a>Internet Websites</a>`.
You can use even a video! WHAAAAAAAAT


Do you want to place your HTML-text on the walls, and make objects clickable,
animated and super-exciting?
We have powerfull and still fantastically easy instruments for that.
Here's a demo:
And here's all the code to create this magic:

As you can see, you can create simple room (photo, and even a VIDEO is possible),
and make the magic with us.

## Quick Start
We have an example quickstart-project for you, which contains this 4 obvious folders:
css/
images/
html/
js/
index.html

The very first step is to add this 3 scripts to the bottom of your index body:
```html
<body>
    <scripts src="js/three.js"></scripts>
    <scripts src="js/CSS3dRenderer.js"></scripts>
    <scripts src="js/room.js"></scripts>
</body>
```
We're using three.js and CSS 3D Renderer just to make this magic happen.
It will not possible without it.

Here how we will create your first room.
Create the file app.js anywhere and place this line of code in it:
```javascript
var guestRoom = Room.create('images/Guest Room/');
```

To place our templates on the walls or objects in this room,
we need to find the good place on the room for it.
We already found it for you:
```javascript
guestRoom.placeTemplate('html/about.html', {});
guestRoom.placeTemplate('html/gallery.html', {});
guestRoom.placeTemplate('html/contact.html', {});
```

We know, that finding of the perfect place for the template is not so easy,
thats why we create powerfull Developers Mode.
You can enable it, placing this one simple line in your file:
`Room.DevelopersMode();`

You can see grey square in your room, and just manipulate of X,Y,Z,angle,width and height
of it to find the perfect place for your template in the room.

Lets make our objects in the room clickable and show the description about them on click.
I decided to make clickable my lamp, TV and mirror.
That is the whole code for the lamp:
```javascript
var lamp = guestRoom.Object({});
lamp.click = function(){
    room.placeTemplate('html/things/lamp.html', {})
}
```
Again, you can easily find the position of your objects using Developers Mode.
Just enable it and play around with parameters.

You can't believe, but we also can create the Second room,
as easily as we create first:
`var kitchen = Room.create('images/Kitchen/');`

And now we can make a guest room door as a way to our second room:
```javascript
var door = guestRoom.Object({});
door.click = function(){
    Room.go(kitchen);
}
```

> You're fully set.

Don't forget to append your app.js file to body of your index.html (after room.js):
```html
    ...
    <script src="js/room.js"></script>
    <script src="app.js"></script>
</body>
```
We have this 30 short and clear lines of code to make it happen.
And that is what you can create if you'll add your imagination to it, my friend: Demo.

## Documentation:

> var yourRoom = Room.create(..)
> yourRoom.placeTemplate(..)
> var yourObj = yourRoom.Object(..)
> Room.go(yourSecondRoom)
> Room.enableDevelopersMode()
> Room.router(..)
> Room.redraw(..)
> yourRoom.templatesReady(..)
> template.click(..)
