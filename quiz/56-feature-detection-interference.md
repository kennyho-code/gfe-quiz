# what's the difference between feature detection, feature interferance, and using the UA string?

## Initial thoughts

- feature detection....if a user is available for a feature?... Feature interference...if a feature interferes doing other actions? ..what is a UA string?

## Research

https://www.greatfrontend.com/questions/quiz/whats-the-difference-between-feature-detection-feature-inference-and-using-the-ua-string

Feature detection... if a browser supports a feature.... there would be code using that feature... else don't use that feature..

ex:

```
if ('geolocation' in navigator) {
  // Can use navigator.geolocation
} else {
  // Handle lack of feature
}
```

feature interfereance
...checks if the function exists..then uses it

```
if (document.getElementsByTagName) {
  element = document.getElementById(id);
}
```

UA string
..user agent strong that comes in headers.... but shouldn't be used

```
navigator.userAgent
```

https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection
