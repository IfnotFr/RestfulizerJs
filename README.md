RestfulizerJs
==========

__Native POST support and hidden "_method" input support for PUT/DELETE__

A simple jQuery plugin for changing the http method (POST/PUT/DELETE) of a simple html link or button.

## How to use

__1:__ Add the `jquery.restfulizer.js` file into your project including jQuery.

```html
  <script type="text/javascript" src="js/jquery.restfulizer.js"></script>
```

__2:__ Use the jQuery method `restfulizer()` on any link you want to customize the method :

```html
<a href="/user/3" data-method="DELETE" class="rest">link</a>
```

```javascript
$(".rest").restfulizer();
```

## Advanced usage

You can also POST links with parameters (and also automatically setup the POST method) :

```html
<a href="/user/create?name=John&age=18&email=test@test.com" class="rest-post">link</a>
```

```javascript
$(".rest-post").restfulizer({
        parse: true,
        method: "POST"
});
```

## Full options usage
```javascript
$(".rest").restfulizer({
        parse: true, // Parse the URL parameters (allow to send them to POST)
        method: "PUT", // The method (POST is native but PUT and DELETE will be simulated with a hidden input called "_method", this solution is handled by many PHP frameworks)
        target: "example.html?specified=yes" // The target (usefull for making non link clickable)
});
```