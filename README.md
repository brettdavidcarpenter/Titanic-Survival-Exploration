# Titanic-Survival-Exploration

This folder contains a binary classifcation project completed as a Part of Udacity's Machine Learning Engineer Nanodegree.

Titanic_Survival_Exploration.ipynb contains an exploratory data analysis of survival rates of passengers aboard the titanic by categories such as age, gender, and socioeconomic class. The findings from this analysis are used to build a prediction model that attempts to predict the survival of an unknown set of passengers.

The model implemented is a decision tree. Tools used include python 2.6 with anaconda, as well as ipython notebook environment.

<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />
<title>titanic_survival_exploration</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>

<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    color: #000 !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.2.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.2.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.2.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.2.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.2.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.2.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=1);
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2);
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=3);
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1);
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1);
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
@media (max-width: 991px) {
  #ipython_notebook {
    margin-left: 10px;
  }
}
[dir="rtl"] #ipython_notebook {
  float: right !important;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#login_widget {
  float: right;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  text-align: center;
  vertical-align: middle;
  display: inline;
  opacity: 0;
  z-index: 2;
  width: 12ex;
  margin-right: -12ex;
}
.alternate_upload .btn-upload {
  height: 22px;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
[dir="rtl"] #tabs li {
  float: right;
}
ul#tabs {
  margin-bottom: 4px;
}
[dir="rtl"] ul#tabs {
  margin-right: 0px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons {
  float: left !important;
}
[dir="rtl"] .list_toolbar .pull-right {
  padding-top: 1px;
  float: left !important;
}
[dir="rtl"] .list_toolbar .pull-left {
  float: right !important;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: baseline;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
#tree-selector {
  padding-right: 0px;
}
[dir="rtl"] #tree-selector a {
  float: right;
}
#button-select-all {
  min-width: 50px;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
[dir="rtl"] #new-menu {
  text-align: right;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
[dir="rtl"] #running .col-sm-8 {
  float: right !important;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI colors. */
.ansibold {
  font-weight: bold;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  border-left-width: 1px;
  padding-left: 5px;
  background: linear-gradient(to right, transparent -40px, transparent 1px, transparent 1px, transparent 100%);
}
div.cell.jupyter-soft-selected {
  border-left-color: #90CAF9;
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected {
  border-color: #ababab;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 5px, transparent 5px, transparent 100%);
}
@media print {
  div.cell.selected {
    border-color: transparent;
  }
}
div.cell.selected.jupyter-soft-selected {
  border-left-width: 0;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 7px, #E3F2FD 7px, #E3F2FD 100%);
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #66BB6A -40px, #66BB6A 5px, transparent 5px, transparent 100%);
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  padding: 0.4em;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. We need the 0 value because of how we size */
  /* .CodeMirror-lines */
  padding: 0;
  border: 0;
  border-radius: 0;
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul {
  list-style: disc;
  margin: 0em 2em;
  padding-left: 0px;
}
.rendered_html ul ul {
  list-style: square;
  margin: 0em 2em;
}
.rendered_html ul ul ul {
  list-style: circle;
  margin: 0em 2em;
}
.rendered_html ol {
  list-style: decimal;
  margin: 0em 2em;
  padding-left: 0px;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin: 0em 2em;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
  margin: 0em 2em;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
  margin: 0em 2em;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
  margin: 0em 2em;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  background-color: #fff;
  color: #000;
  font-size: 100%;
  padding: 0px;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: 1px solid black;
  border-collapse: collapse;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  border: 1px solid black;
  border-collapse: collapse;
  margin: 1em 2em;
}
.rendered_html td,
.rendered_html th {
  text-align: left;
  vertical-align: middle;
  padding: 4px;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget {
  float: right !important;
  float: right;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  margin-top: 6px;
}
span.save_widget span.filename {
  height: 1em;
  line-height: 1em;
  padding: 3px;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  display: none;
}
.command-shortcut:before {
  content: "(command)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}

@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Machine-Learning-Engineer-Nanodegree">Machine Learning Engineer Nanodegree<a class="anchor-link" href="#Machine-Learning-Engineer-Nanodegree">&#182;</a></h1><h2 id="Introduction-and-Foundations">Introduction and Foundations<a class="anchor-link" href="#Introduction-and-Foundations">&#182;</a></h2><h2 id="Project:-Titanic-Survival-Exploration">Project: Titanic Survival Exploration<a class="anchor-link" href="#Project:-Titanic-Survival-Exploration">&#182;</a></h2><p>In 1912, the ship RMS Titanic struck an iceberg on its maiden voyage and sank, resulting in the deaths of most of its passengers and crew. In this introductory project, we will explore a subset of the RMS Titanic passenger manifest to determine which features best predict whether someone survived or did not survive. To complete this project, you will need to implement several conditional predictions and answer the questions below. Your project submission will be evaluated based on the completion of the code and your responses to the questions.</p>
<blockquote><p><strong>Tip:</strong> Quoted sections like this will provide helpful instructions on how to navigate and use an iPython notebook.</p>
</blockquote>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Getting-Started">Getting Started<a class="anchor-link" href="#Getting-Started">&#182;</a></h1><p>To begin working with the RMS Titanic passenger data, we'll first need to <code>import</code> the functionality we need, and load our data into a <code>pandas</code> DataFrame.<br>
Run the code cell below to load our data and display the first few entries (passengers) for examination using the <code>.head()</code> function.</p>
<blockquote><p><strong>Tip:</strong> You can run a code cell by clicking on the cell and using the keyboard shortcut <strong>Shift + Enter</strong> or <strong>Shift + Return</strong>. Alternatively, a code cell can be executed using the <strong>Play</strong> button in the hotbar after selecting it. Markdown cells (text cells like this one) can be edited by double-clicking, and saved using these same shortcuts. <a href="http://daringfireball.net/projects/markdown/syntax">Markdown</a> allows you to write easy-to-read plain text that can be converted to HTML.</p>
</blockquote>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="c1"># Import libraries necessary for this project</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="kn">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="kn">as</span> <span class="nn">pd</span>
<span class="kn">from</span> <span class="nn">IPython.display</span> <span class="kn">import</span> <span class="n">display</span> <span class="c1"># Allows the use of display() for DataFrames</span>

<span class="c1"># Import supplementary visualizations code visuals.py</span>
<span class="kn">import</span> <span class="nn">visuals</span> <span class="kn">as</span> <span class="nn">vs</span>

<span class="c1"># Pretty display for notebooks</span>
<span class="o">%</span><span class="k">matplotlib</span> inline

<span class="c1"># Load the dataset</span>
<span class="n">in_file</span> <span class="o">=</span> <span class="s1">&#39;titanic_data.csv&#39;</span>
<span class="n">full_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="n">in_file</span><span class="p">)</span>

<span class="c1"># Print the first few entries of the RMS Titanic data</span>
<span class="n">display</span><span class="p">(</span><span class="n">full_data</span><span class="o">.</span><span class="n">head</span><span class="p">())</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>


<div class="output_html rendered_html output_subarea ">
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>Braund, Mr. Owen Harris</td>
      <td>male</td>
      <td>22.0</td>
      <td>1</td>
      <td>0</td>
      <td>A/5 21171</td>
      <td>7.2500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>1</td>
      <td>1</td>
      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>
      <td>female</td>
      <td>38.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17599</td>
      <td>71.2833</td>
      <td>C85</td>
      <td>C</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>1</td>
      <td>3</td>
      <td>Heikkinen, Miss. Laina</td>
      <td>female</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>STON/O2. 3101282</td>
      <td>7.9250</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>1</td>
      <td>1</td>
      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>
      <td>female</td>
      <td>35.0</td>
      <td>1</td>
      <td>0</td>
      <td>113803</td>
      <td>53.1000</td>
      <td>C123</td>
      <td>S</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>0</td>
      <td>3</td>
      <td>Allen, Mr. William Henry</td>
      <td>male</td>
      <td>35.0</td>
      <td>0</td>
      <td>0</td>
      <td>373450</td>
      <td>8.0500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>From a sample of the RMS Titanic data, we can see the various features present for each passenger on the ship:</p>
<ul>
<li><strong>Survived</strong>: Outcome of survival (0 = No; 1 = Yes)</li>
<li><strong>Pclass</strong>: Socio-economic class (1 = Upper class; 2 = Middle class; 3 = Lower class)</li>
<li><strong>Name</strong>: Name of passenger</li>
<li><strong>Sex</strong>: Sex of the passenger</li>
<li><strong>Age</strong>: Age of the passenger (Some entries contain <code>NaN</code>)</li>
<li><strong>SibSp</strong>: Number of siblings and spouses of the passenger aboard</li>
<li><strong>Parch</strong>: Number of parents and children of the passenger aboard</li>
<li><strong>Ticket</strong>: Ticket number of the passenger</li>
<li><strong>Fare</strong>: Fare paid by the passenger</li>
<li><strong>Cabin</strong> Cabin number of the passenger (Some entries contain <code>NaN</code>)</li>
<li><strong>Embarked</strong>: Port of embarkation of the passenger (C = Cherbourg; Q = Queenstown; S = Southampton)</li>
</ul>
<p>Since we're interested in the outcome of survival for each passenger or crew member, we can remove the <strong>Survived</strong> feature from this dataset and store it as its own separate variable <code>outcomes</code>. We will use these outcomes as our prediction targets.<br>
Run the code cell below to remove <strong>Survived</strong> as a feature of the dataset and store it in <code>outcomes</code>.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="c1"># Store the &#39;Survived&#39; feature in a new variable and remove it from the dataset</span>
<span class="n">outcomes</span> <span class="o">=</span> <span class="n">full_data</span><span class="p">[</span><span class="s1">&#39;Survived&#39;</span><span class="p">]</span>
<span class="n">data</span> <span class="o">=</span> <span class="n">full_data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="s1">&#39;Survived&#39;</span><span class="p">,</span> <span class="n">axis</span> <span class="o">=</span> <span class="mi">1</span><span class="p">)</span>

<span class="c1"># Show the new dataset with &#39;Survived&#39; removed</span>
<span class="n">display</span><span class="p">(</span><span class="n">data</span><span class="o">.</span><span class="n">head</span><span class="p">())</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>


<div class="output_html rendered_html output_subarea ">
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>PassengerId</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3</td>
      <td>Braund, Mr. Owen Harris</td>
      <td>male</td>
      <td>22.0</td>
      <td>1</td>
      <td>0</td>
      <td>A/5 21171</td>
      <td>7.2500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>1</td>
      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>
      <td>female</td>
      <td>38.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17599</td>
      <td>71.2833</td>
      <td>C85</td>
      <td>C</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>3</td>
      <td>Heikkinen, Miss. Laina</td>
      <td>female</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>STON/O2. 3101282</td>
      <td>7.9250</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>1</td>
      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>
      <td>female</td>
      <td>35.0</td>
      <td>1</td>
      <td>0</td>
      <td>113803</td>
      <td>53.1000</td>
      <td>C123</td>
      <td>S</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>3</td>
      <td>Allen, Mr. William Henry</td>
      <td>male</td>
      <td>35.0</td>
      <td>0</td>
      <td>0</td>
      <td>373450</td>
      <td>8.0500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The very same sample of the RMS Titanic data now shows the <strong>Survived</strong> feature removed from the DataFrame. Note that <code>data</code> (the passenger data) and <code>outcomes</code> (the outcomes of survival) are now <em>paired</em>. That means for any passenger <code>data.loc[i]</code>, they have the survival outcome <code>outcomes[i]</code>.</p>
<p>To measure the performance of our predictions, we need a metric to score our predictions against the true outcomes of survival. Since we are interested in how <em>accurate</em> our predictions are, we will calculate the proportion of passengers where our prediction of their survival is correct. Run the code cell below to create our <code>accuracy_score</code> function and test a prediction on the first five passengers.</p>
<p><strong>Think:</strong> <em>Out of the first five passengers, if we predict that all of them survived, what would you expect the accuracy of our predictions to be?</em></p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">def</span> <span class="nf">accuracy_score</span><span class="p">(</span><span class="n">truth</span><span class="p">,</span> <span class="n">pred</span><span class="p">):</span>
    <span class="sd">&quot;&quot;&quot; Returns accuracy score for input truth and predictions. &quot;&quot;&quot;</span>
    
    <span class="c1"># Ensure that the number of predictions matches number of outcomes</span>
    <span class="k">if</span> <span class="nb">len</span><span class="p">(</span><span class="n">truth</span><span class="p">)</span> <span class="o">==</span> <span class="nb">len</span><span class="p">(</span><span class="n">pred</span><span class="p">):</span> 
        
        <span class="c1"># Calculate and return the accuracy as a percent</span>
        <span class="k">return</span> <span class="s2">&quot;Predictions have an accuracy of {:.2f}%.&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">((</span><span class="n">truth</span> <span class="o">==</span> <span class="n">pred</span><span class="p">)</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">*</span><span class="mi">100</span><span class="p">)</span>
    
    <span class="k">else</span><span class="p">:</span>
        <span class="k">return</span> <span class="s2">&quot;Number of predictions does not match number of outcomes!&quot;</span>
    
<span class="c1"># Test the &#39;accuracy_score&#39; function</span>
<span class="n">predictions</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span> <span class="n">dtype</span> <span class="o">=</span> <span class="nb">int</span><span class="p">))</span>
<span class="k">print</span> <span class="n">accuracy_score</span><span class="p">(</span><span class="n">outcomes</span><span class="p">[:</span><span class="mi">5</span><span class="p">],</span> <span class="n">predictions</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>

<div class="output_subarea output_stream output_stdout output_text">
<pre>Predictions have an accuracy of 60.00%.
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<blockquote><p><strong>Tip:</strong> If you save an iPython Notebook, the output from running code blocks will also be saved. However, the state of your workspace will be reset once a new session is started. Make sure that you run all of the code blocks from your previous session to reestablish variables and functions before picking up where you last left off.</p>
</blockquote>
<h1 id="Making-Predictions">Making Predictions<a class="anchor-link" href="#Making-Predictions">&#182;</a></h1><p>If we were asked to make a prediction about any passenger aboard the RMS Titanic whom we knew nothing about, then the best prediction we could make would be that they did not survive. This is because we can assume that a majority of the passengers (more than 50%) did not survive the ship sinking.<br>
The <code>predictions_0</code> function below will always predict that a passenger did not survive.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">def</span> <span class="nf">predictions_0</span><span class="p">(</span><span class="n">data</span><span class="p">):</span>
    <span class="sd">&quot;&quot;&quot; Model with no features. Always predicts a passenger did not survive. &quot;&quot;&quot;</span>

    <span class="n">predictions</span> <span class="o">=</span> <span class="p">[]</span>
    <span class="k">for</span> <span class="n">_</span><span class="p">,</span> <span class="n">passenger</span> <span class="ow">in</span> <span class="n">data</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
        
        <span class="c1"># Predict the survival of &#39;passenger&#39;</span>
        <span class="n">predictions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
    
    <span class="c1"># Return our predictions</span>
    <span class="k">return</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">predictions</span><span class="p">)</span>

<span class="c1"># Make the predictions</span>
<span class="n">predictions</span> <span class="o">=</span> <span class="n">predictions_0</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Question-1">Question 1<a class="anchor-link" href="#Question-1">&#182;</a></h3><p><em>Using the RMS Titanic data, how accurate would a prediction be that none of the passengers survived?</em><br>
<strong>Hint:</strong> Run the code cell below to see the accuracy of this prediction.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">print</span> <span class="n">accuracy_score</span><span class="p">(</span><span class="n">outcomes</span><span class="p">,</span> <span class="n">predictions</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>

<div class="output_subarea output_stream output_stdout output_text">
<pre>Predictions have an accuracy of 61.62%.
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>Answer:</strong> Predictions have an accuracy of 61.62%.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
<p>Let's take a look at whether the feature <strong>Sex</strong> has any indication of survival rates among passengers using the <code>survival_stats</code> function. This function is defined in the <code>titanic_visualizations.py</code> Python script included with this project. The first two parameters passed to the function are the RMS Titanic data and passenger survival outcomes, respectively. The third parameter indicates which feature we want to plot survival statistics across.<br>
Run the code cell below to plot the survival outcomes of passengers based on their sex.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="n">vs</span><span class="o">.</span><span class="n">survival_stats</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">outcomes</span><span class="p">,</span> <span class="s1">&#39;Sex&#39;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAfgAAAGDCAYAAADHzQJ9AAAABHNCSVQICAgIfAhkiAAAAAlwSFlz
AAALEgAACxIB0t1+/AAAIABJREFUeJzt3XmYXHWd7/H3104gCJE1cAMBEhlUCCQBml0wFxxAiUEd
IEFkwKsCLpC5OirgAogoI+IdNwbh6pAraAhxxMgyoIyACIIJJmgCTNgkgUBCZAkRMAnf+8c5HSqd
XqqX6u6cvF/PU09XnTrLt7b+1O93fnVOZCaSJKla3tDfBUiSpN5nwEuSVEEGvCRJFWTAS5JUQQa8
JEkVZMBLklRBBrzUhyLixIi4pRfWc0pE3NkbNXVz+5dFxBe7sdxOEfFSRDQ1oq7e2H5EZET8XV/W
JTWCAb8Bi4jHI+Ll8h/eMxFxZURs1t919bWIGBERP42IZyPihYj4U0Sc0ohtZebVmXlEI9ZdKyI+
HBEPRsTy8rW9MSKGlvddGRFf6cK61vkykZmnZ+YFdSz7eES8s2a5JzJzs8xc3ZXH08H6vx8R/1Zz
e3BErGhn2gGttx8Rt0XER3qw/fMi4rya2+dExGPlZ2pRRFzT3XXXrHN8RNzWzn0jyy8kL9Vc5vbC
Ns+LiKt6uh71LwNe78nMzYC9gWbgC/1cT0NFxKA2Jv8IWAjsDGwNnAQ804vr71MR8Q7gq8AJmTkU
2A3ocdAMUHcAh9bcbgaeAA5pNQ1gdiMLiYiTKd477yw/U83ArY3cZo0tyi8um2Xm2D7aZrsGwudA
BrxKmfkkcBOwB0BEfCgiHihbgI9GxGkt80bENhFxfUQ8HxF/iYjfRMQbyvs+FxFPlss9FBGHl9Pf
EBFnRcQjEbEsIqZHxFblfS2tkJMj4omyJf35mu1tEhFTI+K5sqbPRsSimvu3L1vgS8vW05k1950X
ETMi4qqIeBE4pY2Hvy9wZWauyMxVmfmHzLypXH587bbKaWtapW2s/5yyV2Srmvn3Kh/T4NrWcET8
W0R8o9W6fx4RnyqvtzxfyyNifkS8r86Xc1/g7sz8A0Bm/iUzp2bm8og4FTgR+GzZ2vtFR9uKiN2A
y4ADy/mfL6ev6QVo7/0QET8CdgJ+US772ZrXelC57FYR8e8R8VT5+l7X0TrbeKx3ALtFxDbl7UOA
acCmrabdnZkra7cfEReW9323rO+7Net9Z0QsKLf/vYiIOp/3mzPzkfJ5fzozL2+5MyI2j4gfRMTi
8jPylSh3FZTvhZ/WzPsvEXFrndttV0T8r/Iz81xE3BwRO9fc962IWBgRL0bE7Ig4pJx+FHAOMClq
egSiVW9M1LTya57XD0fEE8B/ldMPiIi7yudxbkSM78njURdlppcN9AI8TtHaANgRmAdcUN4+GtgF
COAdwF+Bvcv7vkbxT39weTmknO+tFC3h7cv5RgK7lNenAL8DRgAbA98HflIzXwJXAJsAY4FXgd3K
+y8Cbge2LJe/H1hU3vcGipbZl4CNgDcDjwJHlvefB6wE3lvOu0kbz8OvgN8Ck4GdWt03vmVb7Txv
66yf4p/bR2vmvxi4rLx+CnBnef3Q8vmK8vaWwMs1z99xwPbleicBK4DhrdfTxuM5pFzP+cDBwMat
7r8S+EqraV3aVu062ns/tH6uWr3Wg8rbN1D0LmxZLvuOztbZxuN9DHhfef164DDg6lbTvtTO9m8D
PtJqfVkuswXFF5SlwFF1fJ4+CPwF+AxF672p1f0/o3jfbwpsC9wLnFbe90bgv8vn+hDgWWBEHdtc
6/G0uu8Y4GGKHpxBFL1zd7Wqd+vyvk8DTwNDat7XV7X3vm89T00d/698fJsAOwDLgHdTvK/+vrw9
rL//920oF1vwuq5sld1JEaJfBcjMGzLzkSzcDtzC692eK4HhwM6ZuTIzf5PFp3w1RXjvHhGDM/Px
LFszwOnA5zNzUWa+SvHP4dhYuyvv/Mx8OTPnAnMpgh7geOCrmflcZi4Cvl2zzL4U/zC+nJl/y8xH
Kb4oTK6Z5+7MvC4zX8vMl9t4Do4DfgN8EXgsIuZExL5deA5br//HwAkAZQtscjmttd9Q/FNseV6P
Ldf1FEBmXpuZT5XrvQZYAOzXWTGZ+Rvg/RS7XW4AlkXEN6ODgWXd3VapvfdDhyJiOPAu4PTytV1Z
vte6us7bgUPLFv5+FF8kf1Mz7eBynq64KDOfz8wngF8D4zpbIDOvAs4Ajiy3tyQiPlc+1u0ogu6f
sugpWgL8H8r3aWb+laJ7/5vAVcAZ5Xu9Xs+WreTnI+Kfy2mnA1/LzAcycxXFZ3tcSys+M6/KzGVZ
9FpdQvHZfWsXttmW88rH9zLFF4gbM/PG8n31S2BW+TyoDxjwem9mbpGZO2fmx1sCMCLeFRG/K7tH
n6f4ULZ0eV5M0TK4JYru+7MAMvNh4J8owntJREyLiO3LZXYGftbyTwh4gOILwXY1tTxdc/2vQMuA
v+0pWrotaq/vDGxf88/teYruxe3amX8dZbiclZmjy+XmUHzxqbd7tPX6f0rRpT2copX+GkXgtN5u
UnQnn1BO+gBFyxOAiPjH8stGy+Pag9dfgw5l5k2Z+R5gK4qW3ClAu4PJerIt2nk/1GFH4C+Z+VwP
19myH35P4NEyLO+smbYJcE+dNbVo773YoSwGUb6TovV/OnBBRBxJ8T4dDCyueY6/T9GSb1n2Hore
pwCmd7HebcrP8RaZ2bLbZ2fgWzXb+0u57h0AIuKfy+77F8r7N6f+17w9rT+bx7X6bL6d4oub+oAB
r3VExMYUIfUNYLvM3AK4keKfA5m5PDM/nZlvBiYCn4pyX3tm/jgz307x4U7gX8rVLgTeVfNPaIvM
HJLFvv/OLKbomm+xY831hcBjrdY7NDNrWwl1nzIxM58tH/f2FOG4gqL7FICyFTys9WKt1vEcRY/H
JIrQntZB6/MnFD0ZOwP7UzzvlLevAD4JbF2+Bn+ifA268Hhey8xbKXYb7NFWvXVsq8Pnr6P3QyfL
LgS2iogturjO1u6g6O05mte/SM2jeJ8cDfw+M19pr/yOHlt3lb0O11LsTtqD4rG+ytpB/KbySyUA
EfEJilb0U8Bne6GMhRS7AGo/G5tk5l3l/vbPUvSObVm+5i/Q8Wu+1mcB+B9tzFO73ELgR622v2lm
XtTjR6a6GPBqy0YU/2iWAqsi4l3Amp92RcSEiPi7soX7AkVL/LWIeGtEHFZ+QXiFYj/wa+VilwEX
tnQPRsSwiDimznqmA2dHxJYRsQNFELW4F1gexeC+TSKiKSL26EoXezmgaY8oBl4NBT4GPJyZyyj2
iw6JiKMjYjDFfsyN61jtj4F/pOh2b6t7HoAsBsI9C/xfigFaz5d3bUrxz3JpWeOHeD2gO3s8x0TE
5PL5iojYj2Icxe/KWZ6hGKvQorNtPQOMiIiN2tlem++HdrZV+9gXUwzsvLSsdXBEHFrHOluv5+Fy
O1MoA778QnVPOe2OtpbrrL6uimIA5dERMTSKQYbvAkYD95SP9Rbgkoh4U3n/LlH84oGIeAvwFYpu
7ZMoBkF2ulugE5dRfG5Gl9vYPCKOK+8bCqyieM0HRcSXgDfVLPsMMDLWHtg4B5hcvk7NFO/tjlwF
vCcijiw/l0OiGLQ6opPl1EsMeK0jM5cDZ1IE63MUrdCZNbPsSjEw7SXgbuDSzPw1RfBdRBFYT1N0
P55dLvOtch23RMRyirDZv86SvgwsohhM9StgBkVriCx+zzyBYh/pY7welpt34SG/kWIA1PMUXaQ7
U7QaycwXgI+X63ySohVTz77RmRTP09NZjCnoyI+Bd1LzRSAz5wOXUDy/z1B0Nf+2zsfzHPBRiv3o
L1L8o704M1u6/39AMU7i+Yi4ro5t/RdFi/jpiHi2je21936AYrDcF1rtG651EsX+9geBJRS7eDpb
Z1vuoOhZqa37NxTvwY4C/lsUPSjPRcS3O5ivHi9S7B56guK99HXgY5nZcgyBf6T48jyf4jWaAQyP
YhzKVcC/ZObczFxQrudH5ZflbsnMn1H0oE2L4hcef6IY8wBwM/CfFF9g/0zxhby2e/3a8u+yiLiv
vP5FioG3z1EM4Gz3i2u5/YUUu4fOofgisZBiAKK500daRrpK642I+BgwOTPf0d+1SNJA5TcpDXgR
MTwiDi67Nd9K8ZOen/V3XZI0kHm0Ia0PNqIYcTyKoutzGnBpv1YkSQOcXfSSJFWQXfSSJFWQAS9J
UgWt1/vgt9lmmxw5cmR/lyFJUp+ZPXv2s5nZ+oBb61ivA37kyJHMmjWrv8uQJKnPRMSf65nPLnpJ
kirIgJckqYIMeEmSKmi93gcvSerYypUrWbRoEa+80t4J9TRQDRkyhBEjRjB48OBuLW/AS1KFLVq0
iKFDhzJy5EiKk/NpfZCZLFu2jEWLFjFq1KhurcMuekmqsFdeeYWtt97acF/PRARbb711j3peDHhJ
qjjDff3U09fNgJckNVRTUxPjxo1j9OjRjB07lksuuYTXXnsNgFmzZnHmmWe2udzIkSN59tlne7z9
6667jvnz5/d4PV3x7ne/m+eff75Pt9ma++AlaUPS2635Ok5YtskmmzBnzhwAlixZwgc+8AFefPFF
zj//fJqbm2lubu7dmlq57rrrmDBhArvvvnuvrnf16tU0NTW1ed+NN97Yq9vqDlvwkqQ+s+2223L5
5Zfz3e9+l8zktttuY8KECQAsW7aMI444gtGjR/ORj3yE9s52utlmm/H5z3+esWPHcsABB/DMM88A
8Pjjj3PYYYcxZswYDj/8cJ544gnuuusuZs6cyWc+8xnGjRvHI488sta6rr32WvbYYw/Gjh3LoYce
CsCVV17JJz/5yTXzTJgwgdtuu23Ntj/96U8zduxYvva1r3Hcccetma/2sbT0Ppx11ll873vfWzPP
eeedxze+8Q0ALr74Yvbdd1/GjBnDueee25OntU0GvCSpT735zW9m9erVLFmyZK3p559/Pm9/+9uZ
N28e73vf+3jiiSfaXH7FihUccMABzJ07l0MPPZQrrrgCgDPOOIOTTz6Z+++/nxNPPJEzzzyTgw46
iIkTJ3LxxRczZ84cdtlll7XW9eUvf5mbb76ZuXPnMnPmzE5rX7FiBfvvvz9z587lrLPO4p577mHF
ihUAXHPNNUyePHmt+SdNmsT06dPX3J4+fTqTJk3illtuYcGCBdx7773MmTOH2bNnc8cdd3T+5HWB
AS9JGhDuuOMOPvjBDwJw9NFHs+WWW7Y530YbbbSmpbzPPvvw+OOPA3D33XfzgQ98AICTTjqJO++8
s9NtHnzwwZxyyilcccUVrF69utP5m5qa+Id/+AcABg0axFFHHcUvfvELVq1axQ033MAxxxyz1vx7
7bUXS5Ys4amnnmLu3LlsueWW7Ljjjtxyyy3ccsst7LXXXuy99948+OCDLFiwoNPtd4X74CVJferR
Rx+lqamJbbfdlgceeKDLyw8ePHjNCPOmpiZWrVrV7Vouu+wy7rnnHm644Qb22WcfZs+ezaBBg9YM
AgTW+qnakCFD1trvPnnyZL773e+y1VZb0dzczNChQ9fZxnHHHceMGTN4+umnmTRpElD8zv3ss8/m
tNNO63btnbEF31qEl764SNogLV26lNNPP51PfvKT6/wM7NBDD+XHP/4xADfddBPPPfdcl9Z90EEH
MW3aNACuvvpqDjnkEACGDh3K8uXL21zmkUceYf/99+fLX/4yw4YNY+HChYwcOZI5c+bw2muvsXDh
Qu699952t/mOd7yD++67jyuuuGKd7vkWkyZNYtq0acyYMWPNPvsjjzySH/7wh7z00ksAPPnkk+vs
sugpW/CSpIZ6+eWXGTduHCtXrmTQoEGcdNJJfOpTn1pnvnPPPZcTTjiB0aNHc9BBB7HTTjt1aTvf
+c53+NCHPsTFF1/MsGHD+Pd//3egaGV/9KMf5dvf/jYzZsxYaz/8Zz7zGRYsWEBmcvjhhzN27FgA
Ro0axe67785uu+3G3nvv3e42m5qamDBhAldeeSVTp05tc57Ro0ezfPlydthhB4YPHw7AEUccwQMP
PMCBBx4IFIP3rrrqKrbddtsuPeaORHujFNcHzc3N2evng7d12TfW4/edtD554IEH2G233fq7DHVT
W69fRMzOzE5/W2gXvSRJFWTAS5JUQQa8JEkVZMBLklRBBrwkSRVkwEuSVEEGvCSpoS688EJGjx7N
mDFjGDduHPfcc0+P1zlz5kwuuuiiXqiu+A16FXmgG0nagMT5vXusjzy342Na3H333Vx//fXcd999
bLzxxjz77LP87W9/q2vdq1atYtCgtmNq4sSJTJw4scv1bkhswUuSGmbx4sVss802bLzxxgBss802
bL/99mtOpwowa9Ysxo8fDxSnUz3ppJM4+OCDOemkkzjggAOYN2/emvWNHz+eWbNmrTml6wsvvMDO
O++85tjxK1asYMcdd2TlypU88sgjHHXUUeyzzz4ccsghPPjggwA89thjHHjggey555584Qtf6MNn
o28Z8JKkhjniiCNYuHAhb3nLW/j4xz/O7bff3uky8+fP51e/+hU/+clP1jrd6uLFi1m8eDHNza8f
xG3zzTdn3Lhxa9Z7/fXXc+SRRzJ48GBOPfVUvvOd7zB79my+8Y1v8PGPfxyAKVOm8LGPfYw//vGP
aw4dW0UGvCSpYTbbbDNmz57N5ZdfzrBhw5g0aRJXXnllh8tMnDiRTTbZBIDjjz+eGTNmAMW51I89
9th15p80aRLXXHMNANOmTWPSpEm89NJL3HXXXRx33HGMGzeO0047jcWLFwPw29/+lhNOOAEoTitb
Ve6DlyQ1VFNTE+PHj2f8+PHsueeeTJ06da1TstaejhVg0003XXN9hx12YOutt+b+++/nmmuu4bLL
Lltn/RMnTuScc87hL3/5C7Nnz+awww5jxYoVbLHFFsyZM6fNmlqfya6KbMFLkhrmoYceYsGCBWtu
z5kzh5133pmRI0cye/ZsAH760592uI5Jkybx9a9/nRdeeIExY8asc/9mm23Gvvvuy5QpU5gwYQJN
TU286U1vYtSoUVx77bVAcf71uXPnAnDwwQevdVrZqjLgJUkN89JLL3HyySez++67M2bMGObPn895
553Hueeey5QpU2hubqapqanDdRx77LFMmzaN448/vt15Jk2axFVXXcWkSZPWTLv66qv5wQ9+wNix
Yxk9ejQ///nPAfjWt77F9773Pfbcc0+efPLJ3nmgA5Cni21tA+i2GRDW4/edtD7xdLHrN08XK0mS
1mLAS5JUQQa8JEkVZMBLUsWtz2OtNmQ9fd0MeEmqsCFDhrBs2TJDfj2TmSxbtowhQ4Z0ex0e6EaS
KmzEiBEsWrSIpUuX9ncp6qIhQ4YwYsSIbi9vwEtShQ0ePJhRo0b1dxnqB3bRS5JUQQa8JEkVZMBL
klRBBrwkSRVkwEuSVEEGvCRJFWTAS5JUQQa8JEkVZMBLklRBBrwkSRVkwEuSVEEGvCRJFWTAS5JU
QQa8JEkVZMBLklRBBrwkSRVkwEuSVEEND/iIaIqIP0TE9eXtrSLilxGxoPy7Zc28Z0fEwxHxUEQc
2ejaJEmqqr5owU8BHqi5fRZwa2buCtxa3iYidgcmA6OBo4BLI6KpD+qTJKlyGhrwETECOBr4vzWT
jwGmltenAu+tmT4tM1/NzMeAh4H9GlmfJElV1egW/L8CnwVeq5m2XWYuLq8/DWxXXt8BWFgz36Jy
2loi4tSImBURs5YuXdqAkiVJWv81LOAjYgKwJDNntzdPZiaQXVlvZl6emc2Z2Txs2LCelilJUiUN
auC6DwYmRsS7gSHAmyLiKuCZiBiemYsjYjiwpJz/SWDHmuVHlNMkSVIXNawFn5lnZ+aIzBxJMXju
vzLzg8BM4ORytpOBn5fXZwKTI2LjiBgF7Arc26j6JEmqska24NtzETA9Ij4M/Bk4HiAz50XEdGA+
sAr4RGau7of6JEla70WxG3z91NzcnLNmzerdlUb07vrUtvX4fSdJ/SkiZmdmc2fzeSQ7SZIqyICX
JKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySp
ggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIM
eEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJ
kirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpgjoN+IjY
NCLeUF5/S0RMjIjBjS9NkiR1Vz0t+DuAIRGxA3ALcBJwZSOLkiRJPVNPwEdm/hV4P3BpZh4HjG5s
WZIkqSfqCviIOBA4EbihnNbUuJIkSVJP1RPwU4CzgZ9l5ryIeDPw68aWJUmSemJQR3dGRBMwMTMn
tkzLzEeBMxtdmCRJ6r4OW/CZuRp4ex/VIkmSekmHLfjSHyJiJnAtsKJlYmb+R8OqkiRJPVJPwA8B
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
SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmS
KsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirI
gJckqYIMeEmSKsiAlySpggx4SZIqaFB/F6ANU5wf/V3CBiHPzf4uQVI/sQUvSVIFGfCSJFVQwwI+
In4YEUsi4k8107aKiF9GxILy75Y1950dEQ9HxEMRcWSj6pIkaUPQyBb8lcBRraadBdyambsCt5a3
iYjdgcnA6HKZSyOiqYG1SZJUaQ0L+My8A/hLq8nHAFPL61OB99ZMn5aZr2bmY8DDwH6Nqk2SpKrr
633w22Xm4vL608B25fUdgIU18y0qp60jIk6NiFkRMWvp0qWNq1SSpPVYvw2yy8wEuvwbnsy8PDOb
M7N52LBhDahMkqT1X18H/DMRMRyg/LuknP4ksGPNfCPKaZIkqRv6OuBnAieX108Gfl4zfXJEbBwR
o4BdgXv7uDZJkiqjYUeyi4ifAOOBbSJiEXAucBEwPSI+DPwZOB4gM+dFxHRgPrAK+ERmrm5UbZIk
VV3DAj4zT2jnrsPbmf9C4MJG1SNJ0obEI9lJklRBBrwkSRVkwEuSVEEGvCRJFWTAS5JUQQa8JEkV
ZMBLklRBDfsdvCR1S0R/V7BhOK+/C1Cj2YKXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIq
yICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiA
lySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJck
qYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmC
DHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4
SZIqyICXJKmCBlzAR8RREfFQRDwcEWf1dz2SJK2PBlTAR0QT8D3gXcDuwAkRsXv/ViVJ0vpnQAU8
sB/wcGY+mpl/A6YBx/RzTZIkrXcGWsDvACysub2onCZJkrpgUH8X0FURcSpwannzpYh4qD/rUTed
198FdMs2wLP9XURXxHnR3yVooDqvvwvoFj+DhZ3rmWmgBfyTwI41t0eU09bIzMuBy/uyKAkgImZl
ZnN/1yFtqPwMds1A66L/PbBrRIyKiI2AycDMfq5JkqT1zoBqwWfmqoj4JHAz0AT8MDPn9XNZkiSt
dwZUwANk5o3Ajf1dh9QGdw1J/cvPYBdEZvZ3DZIkqZcNtH3wkiSpFxjwUjdExPiIuL6/65DWJxFx
ZkQ8EBFXN2j950XEPzdi3eujAbcPXpJUWR8H3pmZi/q7kA2BLXhtsCJiZEQ8GBFXRsR/R8TVEfHO
iPhtRCyIiP3Ky90R8YeIuCsi3trGejaNiB9GxL3lfB5eWWolIi4D3gzcFBGfb+szExGnRMR1EfHL
iHg8Ij4ZEZ8q5/ldRGxVzvfRiPh9RMyNiJ9GxBvb2N4uEfGfETE7In4TEW/r20fc/wx4bej+DrgE
eFt5+QDwduCfgXOAB4FDMnMv4EvAV9tYx+eB/8rM/YD/CVwcEZv2Qe3SeiMzTweeoviMbEr7n5k9
gPcD+wIXAn8tP393A/9YzvMfmblvZo4FHgA+3MYmLwfOyMx9KD7PlzbmkQ1cdtFrQ/dYZv4RICLm
AbdmZkbEH4GRwObA1IjYFUhgcBvrOAKYWLPvbwiwE8U/Hknrau8zA/DrzFwOLI+IF4BflNP/CIwp
r+8REV8BtgA2ozh2yhoRsRlwEHBtxJpDxW7ciAcykBnw2tC9WnP9tZrbr1F8Pi6g+IfzvogYCdzW
xjoC+IfM9LwIUn3a/MxExP50/pkEuBJ4b2bOjYhTgPGt1v8G4PnMHNe7Za9f7KKXOrY5r58P4ZR2
5rkZOCPKpkJE7NUHdUnrs55+ZoYCiyNiMHBi6zsz80XgsYg4rlx/RMTYHta83jHgpY59HfhaRPyB
9nu8LqDour+/7Oa/oK+Kk9ZTPf3MfBG4B/gtxTiZtpwIfDgi5gLzgA1u8KtHspMkqYJswUuSVEEG
vCRJFWTAS5JUQQa8JEkVZMBLklRBBrykNpXHC58XEfdHxJzyICSS1hMeyU7SOiLiQGACsHdmvhoR
2wAb9XNZkrrAFryktgwHns3MVwEy89nMfCoi9omI28szdN0cEcMjYlB5Zq/xABHxtYi4sD+Ll+SB
biS1oTxZx53AG4FfAdcAdwG3A8dk5tKImAQcmZn/KyJGAzOAM4CLgf0z82/9U70ksIteUhsy86WI
2Ac4hOJ0ntcAX6E4lecvy0OINwGLy/nnRcSPgOuBAw13qf8Z8JLalJmrKc6ed1t5+txPAPMy88B2
FtkTeB7Ytm8qlNQR98FLWkdEvDUidq2ZNI7i/PbDygF4RMTgsmueiHg/sBVwKPCdiNiir2uWtDb3
wUtaR9k9/x1gC2AV8DBwKjAC+DbFaXQHAf8K/Ixi//zhmbkwIs4E9snMk/ujdkkFA16SpAqyi16S
pAoy4CVJqiADXpKkCjLgJUmqIANekqQKMuAlSaogA16SpAoy4CVJqqD/D4fPhy9k8RkrAAAAAElF
TkSuQmCC
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Examining the survival statistics, a large majority of males did not survive the ship sinking. However, a majority of females <em>did</em> survive the ship sinking. Let's build on our previous prediction: If a passenger was female, then we will predict that they survived. Otherwise, we will predict the passenger did not survive.<br>
Fill in the missing code below so that the function will make this prediction.<br>
<strong>Hint:</strong> You can access the values of each feature for a passenger like a dictionary. For example, <code>passenger['Sex']</code> is the sex of the passenger.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">def</span> <span class="nf">predictions_1</span><span class="p">(</span><span class="n">data</span><span class="p">):</span>
    <span class="sd">&quot;&quot;&quot; Model with one feature: </span>
<span class="sd">            - Predict a passenger survived if they are female. &quot;&quot;&quot;</span>
    
    <span class="n">predictions</span> <span class="o">=</span> <span class="p">[]</span>
    <span class="k">for</span> <span class="n">_</span><span class="p">,</span> <span class="n">passenger</span> <span class="ow">in</span> <span class="n">data</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
        
        <span class="c1"># Remove the &#39;pass&#39; statement below </span>
        <span class="c1"># and write your prediction conditions here</span>
        <span class="k">if</span> <span class="n">passenger</span><span class="p">[</span><span class="s1">&#39;Sex&#39;</span><span class="p">]</span> <span class="o">==</span><span class="s1">&#39;female&#39;</span><span class="p">:</span>
            <span class="n">predictions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>
        <span class="k">else</span><span class="p">:</span>
            <span class="n">predictions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
            
    
    <span class="c1"># Return our predictions</span>
    <span class="k">return</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">predictions</span><span class="p">)</span>

<span class="c1"># Make the predictions</span>
<span class="n">predictions</span> <span class="o">=</span> <span class="n">predictions_1</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Question-2">Question 2<a class="anchor-link" href="#Question-2">&#182;</a></h3><p><em>How accurate would a prediction be that all female passengers survived and the remaining passengers did not survive?</em><br>
<strong>Hint:</strong> Run the code cell below to see the accuracy of this prediction.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">print</span> <span class="n">accuracy_score</span><span class="p">(</span><span class="n">outcomes</span><span class="p">,</span> <span class="n">predictions</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>

<div class="output_subarea output_stream output_stdout output_text">
<pre>Predictions have an accuracy of 78.68%.
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>Answer</strong>: Predictions have an accuracy of 78.68%.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
<p>Using just the <strong>Sex</strong> feature for each passenger, we are able to increase the accuracy of our predictions by a significant margin. Now, let's consider using an additional feature to see if we can further improve our predictions. For example, consider all of the male passengers aboard the RMS Titanic: Can we find a subset of those passengers that had a higher rate of survival? Let's start by looking at the <strong>Age</strong> of each male, by again using the <code>survival_stats</code> function. This time, we'll use a fourth parameter to filter out the data so that only passengers with the <strong>Sex</strong> 'male' will be included.<br>
Run the code cell below to plot the survival outcomes of male passengers based on their age.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="n">vs</span><span class="o">.</span><span class="n">survival_stats</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">outcomes</span><span class="p">,</span> <span class="s1">&#39;Age&#39;</span><span class="p">,</span> <span class="p">[</span><span class="s2">&quot;Sex == &#39;female&#39;&quot;</span><span class="p">])</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAfQAAAGDCAYAAADd8eLzAAAABHNCSVQICAgIfAhkiAAAAAlwSFlz
AAALEgAACxIB0t1+/AAAIABJREFUeJzt3Xu4VnWd///n2w0KieUJHRQVaqxRFFAxz0hqaolopaIZ
kTMldmR+9a3QdDz0rSyrGTs4ilPJb7TwUCmeUsc8lmlQYCo65CGFQBBPSFmI7+8fa2282ezDvYF7
783az8d17Wvfa93r8P7cp9f9WWvda0VmIkmSNmwbdXcBkiRp3RnokiRVgIEuSVIFGOiSJFWAgS5J
UgUY6JIkVYCBLq1nEXFyRNy6HpbzkYi4d33UtJbrvzgizlqL+XaMiFcioqkRda2P9UdERsQ/dmVd
UqMZ6BUXEU9FxF/LD7hnI+KyiBjQ3XV1tYgYHBE/jYjnIuKliHgoIj7SiHVl5hWZeXgjll0rIv4l
Ih6NiGXlc3tTRGxW3ndZRPzfTixrjS8PmXlaZn65jnmfiojDauZ7OjMHZObKzrSnneVfEhH/WTPc
NyKWtzFu35brj4g7I+Kj67D+cyLinBbjhkbE67U1rA8R0eaJQVq8l5v/tlvH9Y2JiPnrsgz1HAZ6
73B0Zg4A9gRGAWd2cz0NFRF9Whn938AzwE7AVsAE4Nn1uPwuFREHA18FTsrMzYBdgCu7t6qGuRsY
XTM8CngaOKjFOIBZXVTTh4EXgPERsUkXrRPK93LN35+7cN1r6AnvBb3BQO9FMnMBcDOwG0BEnBIR
c8se3hMRMal52ojYOiJuiIgXI+L5iLgnIjYq7/tiRCwo53ssIg4tx28UEVMi4vGIWBoRV0XEluV9
Q8rNnBMj4umyp/ylmvX1j4hpEfFCWdMXansOEbFd2cNeEhFPRsRnau47JyKuiYjLI+Jl4COtNH9v
4LLMXJ6Zr2Xm7zPz5nL+NXoptb3OVpZ/RtlT2rJm+j3KNvWt7e1GxH9GxDdbLPu6iPhsebv58VoW
EY9ExPvqfDr3Bu7LzN8DZObzmTktM5dFxKnAycAXyl7c9e2tKyJ2AS4G9iunf7Ecv6qX39brISL+
G9gRuL6c9ws1z3Wfct4tI+JHEfHn8vm9tr1lttLWu4FdImLrcvggYDqwaYtx92Xmitr1R8RXyvu+
V9b3vZrlHhYR88r1fz8iop4HvpzuwxRfjFcAR7e4//DyffFSRFwUEXdFzRaCiPjn8jX+QkTcEhE7
1bPeDmraNyJ+XbZlTkSMqbnvlGjlfR4Rm1J8HmwXNT3+aLF1p+X7o3xvfDEiHgSWl49zm+9PdaHM
9K/Cf8BTwGHl7R2Ah4Evl8NHAW8DAjgY+AuwZ3nf1yg+5PuWfweV072Doqe7XTndEOBt5e3JwG+A
wcAmwCXAT2qmS+BSoD8wAvgbsEt5//nAXcAW5fwPAvPL+zai6Hn9G7Ax8FbgCeCI8v5zKD5Yjy2n
7d/K4/A/wK+AE4EdW9w3pnldbTxuaywf+CXwsZrpLwAuLm9/BLi3vD26fLyiHN4C+GvN43c8sF25
3PHAcmBQy+W00p6DyuWcCxwAbNLi/suA/9tiXKfWVbuMtl4PLR+rFs91n3L4RoqtB1uU8x7c0TJb
ae+TwPvK2zcAhwBXtBj3b22s/07goy2Wl+U8m1N8IVkCHFnne+ogitfuFsB3getr7tsaeBl4P9CH
4j2xonn9wDHAHym2qPSh+FLw686+l1uM3x5YCry3fG7fXQ4PrON9PoY1X/urvXZaTlPWMZvi86Q/
Hbw//eu6P3vovcO1Za/rXorQ/CpAZt6YmY9n4S7gVt7YjLkCGATslJkrMvOeLN7NKynCeteI6JuZ
T2Xm4+U8pwFfysz5mfk3iiA8LlbfLHduZv41M+cAcyiCHeAE4KuZ+UJmzge+UzPP3hQfTudl5t8z
8wmKLwYn1kxzX2Zem5mvZ+ZfW3kMjgfuAc4CnoyI2RGxdycew5bL/zFwEqzqsZ1YjmvpHorwaH5c
jyuX9WeAzLw6M/9cLvdKYB7wzo6Kycx7KEJjT4rAXBoR3452DgRb23WV2no9tCsiBgHvAU4rn9sV
5Wuts8u8Cxhd9uDfSfHF8Z6acQeU03TG+Zn5YmY+DdwBjKxzvonAzZn5AsVzfmREbFPe917g4cz8
WWa+RvE6XlQz72nA1zJzbnn/V4GRneilX1v2wl9s3tIBfAi4KTNvKp/b24CZZS0dvc/X1ncy85ny
vVDP+1NdwEDvHY7NzM0zc6fM/ERz4EXEeyLiN+XmzhcpPgCaN2FeQNGTuLXcTDcFIDP/CPwrRVgv
jojp8caBOTsBP2/+wAHmUnwB2LamltoPt78AzQfobUfRk21We3snis2CL9Ys+4wWy62dfg1lmEzJ
zGHlfLMpPhzr2szayvJ/SrGJehBFL/x1ioBpud6k2Dx8UjnqgxQ9SwAi4sPll4vmdu3GG89BuzLz
5sw8GtiSouf3EaDNg7/WZV208Xqoww7A82X4rcsym/ej7w48kZl/ofiC2jyuP3B/nTU1a+u12KaI
6E/x5fAKgMy8j2J//gfLSVZ7HZfPf+3unJ2AC2ueg+cpes7b11lz83t588w8tmaZx7d4fxxI8WWp
o/f52urs+1NdwEDvpaI4kOenwDeBbTNzc+Amig8XMnNZZn4uM98KjAM+G+W+8sz8cWYeSPFGTuDr
5WKfAd5T84GzeWb2y2LffUcWUmxqb7ZDze1ngCdbLHezzHxvzTR1XzYwM58r270dRRguB97UfH/Z
yx3YcrYWy3iBoqcznuLDfHo7vcufUGyp2AnYh+Jxpxy+FPgUsFX5HDxE+Rx0oj2vZ+btFLsBdmut
3jrW1e7j197roYN5nwG2jIjNO7nMlu6m2JpzFG98cXqY4nVyFPDbzHy1rfLba1snvQ94M3BRRCyK
iEUUYTyxvH+113H5hbH2df0MMKnFa7l/Zv56HWp6BvjvFsvcNDPP7+h9TuuPzWrvB+AfWpmmdr56
3p/qAgZ677UxxabzJcBrEfEeYNVPrSJibET8Y/mB9BJFT/v1iHhHRBxSflC8SrEf9/VytouBrzRv
PoyIgRFxTJ31XAWcHhFbRMT2FMHT7AFgWXkgTv+IaIqI3TqzyTwivl7O0yeKn3Z9HPhjZi4F/hfo
FxFHRURfiv2a9Ry5/GOKg6OOo/XN7QBkceDac8B/Abdk5ovlXZtSfDAuKWs8hTcCuaP2HBMRJ5aP
V0TEOyn2j/6mnORZin2ZzTpa17PA4IjYuI31tfp6aGNdtW1fSHHg1UVlrX0jYnQdy2y5nD+W65lM
GejlF6j7y3F3tzZfR/WthYnADym2Cows/w4ARkTE7hS7P3aPiGPLXU2fZPVAvJjidT4MICLeEhHH
r2NNlwNHR8QR5XujXxQHsg2mg/c5xWOzVUS8pWbcbOC9URzM+A8UW+Tas87vT60fBnovlZnLgM9Q
BOkLFL3MGTWT7ExxINkrwH3ARZl5B8WHw/kUAbUI2AY4vZznwnIZt0bEMopw2afOks6j2DT5ZLne
aygOPCKL3xOPpfjwfJI3wvEtrS6pdW8Cfg68SHHAzk4UvUIy8yXgE+UyF1D0UOr5be4MisdpURbH
BLTnx8Bh1AR/Zj4CfIvi8X2WIiR+VWd7XgA+RrEf/GWKD/ULMrN5c/4PKI5zeDEirq1jXb+k6PEu
iojnWllfW68HKA5uO7Nc1/9pZd4JFPvLHwUW80ZAtLfM1txNseWktu57KF6D7QX6hRRbSF6IiO+0
M127yi+ahwL/kZmLav5mAb8AJpZbf44HvkFxYNquFPuzm1/LP6fYojU9il9MPERxjMFay8xnKHa5
nEER3M8Anwc26uh9npmPUmxBeqJ8/raj+InnHIqD326lg59Drqf3p9aD5qNUpR4lIj4OnJiZB3d3
LdLaiuKAvfnAyR18WZHWmT109QgRMSgiDojit83vAD5H0aOWNijlpu/Ny91SZ1Dsr/5NB7NJ68yz
/Kin2Jjid+tDKTaLTwcu6taKpLWzH8WulY2BRyiOTG/tp5TSeuUmd0mSKsBN7pIkVYCBLklSBWwQ
+9C33nrrHDJkSHeXIUlSl5g1a9ZzmdnyBFft2iACfciQIcycObO7y5AkqUtExJ86O4+b3CVJqgAD
XZKkCjDQJUmqgA1iH7okqW0rVqxg/vz5vPpqWxecU0/Vr18/Bg8eTN++fdd5WQa6JG3g5s+fz2ab
bcaQIUMoLl6nDUFmsnTpUubPn8/QoUPXeXlucpekDdyrr77KVlttZZhvYCKCrbbaar1tWTHQJakC
DPMN0/p83gx0SdI6a2pqYuTIkQwbNowRI0bwrW99i9dffx2AmTNn8pnPfKbV+YYMGcJzzz23zuu/
9tpreeSRR9Z5OZ3x3ve+lxdffLFL19ke96FLUtVMmrR+l3fJJR1O0r9/f2bPng3A4sWL+eAHP8jL
L7/Mueeey6hRoxg1atT6ramFa6+9lrFjx7Lrrruu1+WuXLmSpqamVu+76aab1uu61pU9dEnSerXN
NtswdepUvve975GZ3HnnnYwdOxaApUuXcvjhhzNs2DA++tGP0tYVPwcMGMCXvvQlRowYwb777suz
zz4LwFNPPcUhhxzC8OHDOfTQQ3n66af59a9/zYwZM/j85z/PyJEjefzxx1db1tVXX81uu+3GiBEj
GD16NACXXXYZn/rUp1ZNM3bsWO68885V6/7c5z7HiBEj+NrXvsbxxx+/arratjRvXZgyZQrf//73
V01zzjnn8M1vfhOACy64gL333pvhw4dz9tlnr8vD2iEDXZK03r31rW9l5cqVLF68eLXx5557Lgce
eCAPP/ww73vf+3j66adbnX/58uXsu+++zJkzh9GjR3PppZcC8OlPf5qJEyfy4IMPcvLJJ/OZz3yG
/fffn3HjxnHBBRcwe/Zs3va2t622rPPOO49bbrmFOXPmMGPGjA5rX758Ofvssw9z5sxhypQp3H//
/SxfvhyAK6+8khNPPHG16cePH89VV121aviqq65i/Pjx3HrrrcybN48HHniA2bNnM2vWLO6+++6O
H7y1ZKBLkrrM3XffzYc+9CEAjjrqKLbYYotWp9t4441X9YT32msvnnrqKQDuu+8+PvjBDwIwYcIE
7r333g7XecABB/CRj3yESy+9lJUrV3Y4fVNTEx/4wAcA6NOnD0ceeSTXX389r732GjfeeCPHHHPM
atPvscceLF68mD//+c/MmTOHLbbYgh122IFbb72VW2+9lT322IM999yTRx99lHnz5nW4/rXlPnRJ
0nr3xBNP0NTUxDbbbMPcuXM7PX/fvn1XHQHe1NTEa6+9tta1XHzxxdx///3ceOON7LXXXsyaNYs+
ffqsOmgPWO2nY/369Vttv/mJJ57I9773PbbccktGjRrFZptttsY6jj/+eK655hoWLVrE+PHjgeJ3
5qeffjqT1vcxDW0w0NWjTbq+a94IPdUlR3d8MJLU0yxZsoTTTjuNT33qU2v8LGv06NH8+Mc/5swz
z+Tmm2/mhRde6NSy999/f6ZPn86ECRO44oorOOiggwDYbLPNWLZsWavzPP744+yzzz7ss88+3Hzz
zTzzzDMMGTKEiy66iNdff50FCxbwwAMPtLnOgw8+mH/+53/m0ksvXWNze7Px48fzsY99jOeee467
7roLgCOOOIKzzjqLk08+mQEDBrBgwQL69u3LNtts06k218tAlySts7/+9a+MHDmSFStW0KdPHyZM
mMBnP/vZNaY7++yzOemkkxg2bBj7778/O+64Y6fW893vfpdTTjmFCy64gIEDB/KjH/0IKHrRH/vY
x/jOd77DNddcs9p+9M9//vPMmzePzOTQQw9lxIgRAAwdOpRdd92VXXbZhT333LPNdTY1NTF27Fgu
u+wypk2b1uo0w4YNY9myZWy//fYMGjQIgMMPP5y5c+ey3377AcXBdpdffnnDAj3aOsKwJxk1alR6
PfTeyR66PXR1bO7cueyyyy7dXYbWUmvPX0TMysxO/dbPg+IkSaoAA12SpAow0CVJqgADXZKkCjDQ
JUmqAANdkqQKaGigR8RTEfGHiJgdETPLcVtGxG0RMa/83/p5/yRJG5SvfOUrDBs2jOHDhzNy5Eju
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
MjAmki8AAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Examining the survival statistics, the majority of males younger than 10 survived the ship sinking, whereas most males age 10 or older <em>did not survive</em> the ship sinking. Let's continue to build on our previous prediction: If a passenger was female, then we will predict they survive. If a passenger was male and younger than 10, then we will also predict they survive. Otherwise, we will predict they do not survive.<br>
Fill in the missing code below so that the function will make this prediction.<br>
<strong>Hint:</strong> You can start your implementation of this function using the prediction code you wrote earlier from <code>predictions_1</code>.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">def</span> <span class="nf">predictions_2</span><span class="p">(</span><span class="n">data</span><span class="p">):</span>
    <span class="sd">&quot;&quot;&quot; Model with two features: </span>
<span class="sd">            - Predict a passenger survived if they are female.</span>
<span class="sd">            - Predict a passenger survived if they are male and younger than 10. &quot;&quot;&quot;</span>
    
    <span class="n">predictions</span> <span class="o">=</span> <span class="p">[]</span>
    <span class="k">for</span> <span class="n">_</span><span class="p">,</span> <span class="n">passenger</span> <span class="ow">in</span> <span class="n">data</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
        
        <span class="c1"># Remove the &#39;pass&#39; statement below </span>
        <span class="c1"># and write your prediction conditions here</span>
        <span class="k">if</span> <span class="n">passenger</span><span class="p">[</span><span class="s1">&#39;Sex&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s1">&#39;female&#39;</span><span class="p">:</span> 
            <span class="n">predictions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>
        <span class="k">elif</span> <span class="n">passenger</span><span class="p">[</span><span class="s1">&#39;Sex&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s1">&#39;male&#39;</span> <span class="ow">and</span> <span class="n">passenger</span><span class="p">[</span><span class="s1">&#39;Age&#39;</span><span class="p">]</span> <span class="o">&lt;</span> <span class="mi">10</span><span class="p">:</span>
            <span class="n">predictions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>
        <span class="k">else</span><span class="p">:</span>
            <span class="n">predictions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
    
    <span class="c1"># Return our predictions</span>
    <span class="k">return</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">predictions</span><span class="p">)</span>

<span class="c1"># Make the predictions</span>
<span class="n">predictions</span> <span class="o">=</span> <span class="n">predictions_2</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Question-3">Question 3<a class="anchor-link" href="#Question-3">&#182;</a></h3><p><em>How accurate would a prediction be that all female passengers and all male passengers younger than 10 survived?</em><br>
<strong>Hint:</strong> Run the code cell below to see the accuracy of this prediction.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">print</span> <span class="n">accuracy_score</span><span class="p">(</span><span class="n">outcomes</span><span class="p">,</span> <span class="n">predictions</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>

<div class="output_subarea output_stream output_stdout output_text">
<pre>Predictions have an accuracy of 79.35%.
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>Answer</strong>: Predictions have an accuracy of 79.35%.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<hr>
<p>Adding the feature <strong>Age</strong> as a condition in conjunction with <strong>Sex</strong> improves the accuracy by a small margin more than with simply using the feature <strong>Sex</strong> alone. Now it's your turn: Find a series of features and conditions to split the data on to obtain an outcome prediction accuracy of at least 80%. This may require multiple features and multiple levels of conditional statements to succeed. You can use the same feature multiple times with different conditions.<br>
<strong>Pclass</strong>, <strong>Sex</strong>, <strong>Age</strong>, <strong>SibSp</strong>, and <strong>Parch</strong> are some suggested features to try.</p>
<p>Use the <code>survival_stats</code> function below to to examine various survival statistics.<br>
<strong>Hint:</strong> To use mulitple filter conditions, put each condition in the list passed as the last argument. Example: <code>["Sex == 'male'", "Age &lt; 18"]</code></p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[22]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="n">vs</span><span class="o">.</span><span class="n">survival_stats</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">outcomes</span><span class="p">,</span> <span class="s1">&#39;Pclass&#39;</span><span class="p">,</span> <span class="p">[</span><span class="s2">&quot;Sex == &#39;female&#39;&quot;</span><span class="p">])</span>
<span class="n">vs</span><span class="o">.</span><span class="n">survival_stats</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">outcomes</span><span class="p">,</span> <span class="s1">&#39;Pclass&#39;</span><span class="p">,</span> <span class="p">[</span><span class="s2">&quot;Sex == &#39;male&#39;&quot;</span><span class="p">])</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
JGmVe//738/y5ctZsGDBO8afe+657LPPPjzyyCN87GMf4+mnn25z/qVLl7LHHnswc+ZM9ttvPy67
7DIAPve5z3H88cfz8MMPc9xxx3H66aez1157MWbMGM4//3xmzJjBtttu+45lff3rX+cXv/gFM2fO
5Oabb+609qVLl7L77rszc+ZMzjjjDKZOncrSpUsBuOaaazjmmGPeMf24ceO49tprVwxfe+21jBs3
jjvuuIM5c+bwwAMPMGPGDKZPn869997b+YvXRQa5JKnH3HvvvXzyk58E4PDDD2fjjTduc7p11113
Rct311135amnngLg/vvv5xOf+AQA48eP5ze/+U2n69x777054YQTuOyyy1i+fHmn0zc1NfGP//iP
APTp04dDDz2Un/3sZ7z55pvceuutHHHEEe+Yfuedd2bBggU8++yzzJw5k4033pitttqKO+64gzvu
uIOdd96ZXXbZhUcffZQ5c+Z0uv6uch+5JGmVe+KJJ2hqamKzzTZj9uzZXZ6/b9++K3p0NzU18eab
b650LZdccglTp07l1ltvZdddd2X69On06dNnRWc84B2HgPXr1+8d+8WPOeYYLrroIjbZZBNGjRrF
hhtu+K51jB07luuvv57nnnuOcePGAcVx4l/5ylc45ZRTVrr2KgzyNVicu3YcjpITO++II6nnLFy4
kFNPPZXTTjvtXYdX7bffflx11VWcddZZ3H777bz44otdWvZee+3FlClTGD9+PJMnT2bfffcFYMMN
N2TJkiVtzvP444+z++67s/vuu3P77bczd+5chg4dysUXX8xbb73FM888wwMPPNDuOvfff3/++Z//
mcsuu+xdm9WbjRs3jpNOOolFixZxzz33AHDIIYdw9tlnc9xxxzFgwACeeeYZ+vbty2abbdal59wZ
g1yS1G2vvfYaI0eOZNmyZfTp04fx48fz+c9//l3TTZw4kWOPPZZhw4ax11578b73va9L6/nBD37A
iSeeyPnnn8+gQYP48Y9/DBSt5pNOOokLL7yQ66+//h37yb/4xS8yZ84cMpODDjqIESNGALDNNtuw
ww47sP3227PLLru0u86mpiZGjx7NFVdcwaRJk9qcZtiwYSxZsoQtt9ySwYMHA3DwwQcze/Zs9txz
T6DoRHfllVeu8iCP9noMrk5GjRqVXo+862yRS2uH2bNns/322/d2GVpJbb1/ETE9Mysds2dnN0mS
aswglySpxgxySZJqzCCXJKnGDHJJkmrMIJckqcYMcknSKvHNb36TYcOGMXz4cEaOHMnUqVO7vcyb
b76Z8847bxVUVxzHvSbyhDCStIZZ1eeQqHKuhvvvv59bbrmFBx98kPXWW49FixbxxhtvVFr+m2++
SZ8+bcfRmDFjGDNmTJfqXdvYIpckddv8+fPZdNNNWW+99QDYdNNN2WKLLVZc6hNg2rRpHHDAAUBx
qc/x48ez9957M378ePbYYw8eeeSRFcs74IADmDZt2orLjb788stsvfXWK86PvnTpUrbaaiuWLVvG
448/zqGHHsquu+7Kvvvuy6OPPgrAk08+yZ577slOO+3EWWed1YOvRs8yyCVJ3XbwwQczd+5cPvjB
D/LZz352xfnGOzJr1ix+9atfcfXVV7/jUqDz589n/vz5jBr19onN3vve9zJy5MgVy73llls45JBD
6Nu3LyeffDI/+MEPmD59OhdccAGf/exnAZgwYQKf+cxn+OMf/7jitKlrIoNcktRtAwYMYPr06Vx6
6aUMGjSIcePGccUVV3Q4z5gxY+jfvz8ARx99NNdffz1QXM/7qKOOetf048aN45prrgFgypQpjBs3
jldffZXf/e53jB07lpEjR3LKKacwf/58AH77299y7LHHAsUlT9dU7iOXJK0STU1NHHDAARxwwAHs
tNNOTJo06R2XC215qVCADTbYYMX9LbfckoEDB/Lwww9zzTXXcMkll7xr+WPGjOHMM8/khRdeYPr0
6Rx44IEsXbqUjTbaiBkzZrRZU+urr62JbJFLkrrtscceY86cOSuGZ8yYwdZbb83QoUOZPn06ADfc
cEOHyxg3bhzf+c53ePnllxk+fPi7Hh8wYAC77bYbEyZMYPTo0TQ1NfGe97yHbbbZhuuuuw4orgE+
c+ZMAPbee2+mTJkCwOTJk1fJ81wdGeSSpG579dVXOf7449lhhx0YPnw4s2bN4pxzzmHixIlMmDCB
UaNG0dTU1OEyjjrqKKZMmcLRRx/d7jTjxo3jyiuvZNy4cSvGTZ48mcsvv5wRI0YwbNgwbrrpJgC+
//3v88Mf/pCddtqJZ555ZtU80dWQlzFdg3kZU2nt4GVM683LmEqStBYzyCVJqjGDXJKkGjPIJWkN
UIf+Tnq3VfG+GeSSVHP9+vVj8eLFhnnNZCaLFy+mX79+3VqOJ4SRpJobMmQI8+bNY+HChb1dirqo
X79+DBkypFvLMMglqeb69u3LNtts09tlqJe4aV2SpBozyCVJqjGDXJKkGjPIJUmqMYNckqQaM8gl
Saoxg1ySpBozyCVJqjGDXJKkGmtokEfE/4qIRyLiTxFxdUT0i4hNIuKXETGn/LtxI2uQJGlN1rAg
j4gtgdOBUZm5I9AEHAOcAdyZmR8A7iyHJUnSSmj0pvU+QP+I6AOsDzwLHAFMKh+fBBzZ4BokSVpj
NSzIM/MZ4ALgaWA+8HJm3gFsnpnzy8meAzZvVA2SJK3pGrlpfWOK1vc2wBbABhHxyZbTZHHx3DYv
oBsRJ0fEtIiY5qX5JElqWyM3rX8YeDIzF2bmMuAnwF7A8xExGKD8u6CtmTPz0swclZmjBg0a1MAy
JUmqr0YG+dPAHhGxfkQEcBAwG7gZOL6c5njgpgbWIEnSGq1PoxacmVMj4nrgQeBN4CHgUmAAcG1E
fAr4C3B0o2qQJGlN17AgB8jMicDEVqP/RtE6lyRJ3eSZ3SRJqjGDXJKkGjPIJUmqMYNckqQaM8gl
Saoxg1ySpBozyCVJqjGDXJKkGjPIJUmqMYNckqQaM8glSaoxg1ySpBozyCVJqjGDXJKkGjPIJUmq
MYNckqQaM8glSaoxg1ySpBozyCVJqjGDXJKkGjPIJUmqMYNckqQa69PbBUjSWimityvoEXFOb1fQ
M3Ji9tq6bZFLklRjBrkkSTVmkEuSVGMGuSRJNWaQS5JUYwa5JEk15uFnktoV564dh0j15qFDUnfZ
IpckqcYMckmSaswglySpxgxySZJqzCCXJKnGDHJJkmrMIJckqcYMckmSaswglySpxgxySZJqzCCX
JKnGDHJJkmrMIJckqcYMckmSaswglySpxgxySZJqzCCXJKnGDHJJkmrMIJckqcYMckmSaqzTII+I
DSJinfL+ByNiTET0bXxpkiSpM1Va5PcC/SJiS+AOYDxwRSOLkiRJ1VQJ8sjMvwIfBy7OzLHAsMaW
JUmSqqgU5BGxJ3AccGs5rqlxJUmSpKqqBPkE4CvATzPzkYh4P3BXY8uSJElV9OnowYhoAsZk5pjm
cZn5BHB6owuTJEmd67BFnpnLgX16qBZJktRFHbbISw9FxM3AdcDS5pGZ+ZOGVSVJkiqpEuT9gMXA
gS3GJWCQS5LUyzoN8sw8sScKkSRJXVflzG4fjIg7I+JP5fDwiDirysIjYqOIuD4iHo2I2RGxZ0Rs
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
Bha0NW9mXpqZozJz1KBBgxpZpiRJtdXIXusBXA7MzszvtXjoZuD48v7xwE2NqkGSpDVdnwYue29g
PPDHiJhRjjsTOA+4NiI+BfwFOLqBNUiStEZrWJBn5m+AaOfhgxq1XkmS1iae2U2SpBozyCVJqjGD
XJKkGjPIJUmqMYNckqQaM8glSaoxg1ySpBozyCVJqjGDXJKkGjPIJUmqMYNckqQaM8glSaoxg1yS
pBozyCVJqjGDXJKkGjPIJUmqMYNckqQaM8glSaoxg1ySpBozyCVJqjGDXJKkGjPIJUmqMYNckqQa
M8glSaoxg1ySpBozyCVJqjGDXJKkGjPIJUmqMYNckqQaM8glSaoxg1ySpBozyCVJqjGDXJKkGjPI
JUmqMYNckqQaM8glSaoxg1ySpBozyCVJqjGDXJKkGjPIJUmqMYNckqQaM8glSaoxg1xaGRFrx03S
as8glySpxgxySZJqzCCXJKnGDHJJkmrMIJckqcYMckmSaswglySpxgxySZJqzCCXJKnGDHJJkmps
7Qzy3j7tpafXlCStImtnkEuStIYwyCVJqjGDXJKkGjPIJUmqMYNckqQa65Ugj4hDI+KxiPhzRJzR
GzVIkrQm6PEgj4gm4IfAR4AdgGMjYoeerkOSpDVBb7TIPwT8OTOfyMw3gCnAEb1QhyRJtdcbQb4l
MLfF8LxynCRJ6qLIzJ5dYcRRwKGZ+elyeDywe2ae1mq6k4GTy8HtgMd6tFCtrE2BRb1dhGrNz5C6
a034DG2dmYOqTNin0ZW04RlgqxbDQ8px75CZlwKX9lRRWjUiYlpmjurtOlRffobUXWvbZ6g3Nq3/
AfhARGwTEesCxwA390IdkiTVXo+3yDPzzYg4DfgF0AT8n8x8pKfrkCRpTdAbm9bJzNuA23pj3Wo4
d4eou/wMqbvWqs9Qj3d2kyRJq46naJUkqcYMcq0SEfF/ImJBRPypt2tRPUXEVhFxV0TMiohHImJC
b9ekeomIfhHxQETMLD9D5/Z2TT3BTetaJSJiP+BV4P9m5o69XY/qJyIGA4Mz88GI2BCYDhyZmbN6
uTTVREQEsEFmvhoRfYHfABMy8/e9XFpD2SLXKpGZ9wIv9HYdqq/MnJ+ZD5b3lwCz8ayP6oIsvFoO
9i1va3xr1SCXtNqJiKHAzsDU3q1EdRMRTRExA1gA/DIz1/jPkEEuabUSEQOAG4B/zcxXerse1Utm
Ls/MkRRnDf1QRKzxu/oMckmrjXK/5g3A5Mz8SW/Xo/rKzJeAu4BDe7uWRjPIJa0Wyo5KlwOzM/N7
vV2P6iciBkXERuX9/sA/AI/2blWNZ5BrlYiIq4H7ge0iYl5EfKq3a1Lt7A2MBw6MiBnl7bDeLkq1
Mhi4KyIepriuxy8z85ZerqnhPPxMkqQas0UuSVKNGeSSJNWYQS5JUo0Z5JIk1ZhBLklSjRnk0log
IpaXh3P9KSKui4j1O5j2nIj43z1Zn6SVZ5BLa4fXMnNkeWW6N4BTe7sgSauGQS6tfe4D/g4gIv4p
Ih4ur9/8360njIiTIuIP5eM3NLfkI2Js2bqfGRH3luOGldeCnlEu8wM9+qyktZQnhJHWAhHxamYO
iIg+FOcy/zlwL/BTYK/MXBQRm2TmCxFxDvBqZl4QEQMzc3G5jH8Dns/MH0TEH4FDM/OZiNgoM1+K
iB8Av8/MyRGxLtCUma/1yhOW1iK2yKW1Q//y0o7TgKcpzml+IHBdZi4CyMy2rie/Y0TcVwb3ccCw
cvxvgSsi4iSgqRx3P3BmRHwZ2NoQl3pGn94uQFKPeK28tOMKxTVKOnUFcGRmzoyIE4ADADLz1IjY
HTgcmB4Ru2bmVRExtRx3W0Sckpm/XoXPQVIbbJFLa69fA2MjYiBARGzSxjQbAvPLy4se1zwyIrbN
zKmZ+TVgIbBVRLwfeCIzLwRuAoY3/BlIskUura0y85GI+CZwT0QsBx4CTmg12dnAVIqwnkoR7ADn
l53ZArgTmAl8GRgfEcuA54BvNfxJSLKzmyRJdeamdUmSaswglySpxgxySZJqzCCXJKnGDHJJkmrM
IJckqcYMckmSaswglySpxv4/jRYpuqNkfhQAAAAASUVORK5CYII=
"
>
</div>

</div>

<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
diz77bcf22+//Tpt5wc/+AEnn3wy559/PsOGDeM//uM/gKKVfcopp/D973+fa6+99k374b/4xS/y
8MMPk5kccsghjBs3DoDRo0czZswYdt55Z/bYY492t9nU1MRRRx3FpZdeymWXXdbmPGPHjmXFihVs
t912DB8+HIBDDz2UBx54gPe85z1AMXjvpz/9KVtvvfU6PWZJUn2ivZHbPb6hiK8BfwVOASZk5pKI
GA7ckZnvjogzATLzW+X8vwbOzsx2u+ibm5uz9fngH3jgAXbeeedGPQw1mP8/rffWl9ZtL2VPFUXE
nMzs9PfWjRxFP6xsuRMRGwPvBx4EZgInlrOdCPy8vD4TmBwRG0XEaGAnoP2+YkmS1K5GdtEPBy4r
R8JvAFydmTdExD3A1RHxceAvwHEAmTk/Iq4GFgCvAZ8uu/glSdI6auQo+vuB3duYvhw4pJ1lzgXO
bVRNkiStLzySnSRJFWTAS5JUQQa8JEkVZMA3yLnnnsvYsWPZbbfdGD9+PLNmzer2OmfOnMl5553X
A9UVv0OXJFVX5U8XG+f07G9Kc1rnv9285557uOGGG7jvvvvYaKONePbZZ/nb3/5W1/pfe+01Bg1q
+98yceJEJk6cuE71SpLWT7bgG2DJkiVstdVWbLTRRgBstdVWbLvttmtPqQowe/ZsJkyYABSnVJ0y
ZQr7778/U6ZMYd9992X+/Plr1zdhwgRmz5699rSuL774IjvssMPa48evWrWKkSNHsnr1ah599FEO
P/xw9txzTw488EAefPBBAB5//HHe8573sOuuu/KVr3ylF58NSVJfMOAb4NBDD2XhwoW8613v4lOf
+hR33nlnp8ssWLCAW2+9lSuvvPJNp1xdsmQJS5Ysobn5jYMWveMd72D8+PFr13vDDTdw2GGHMXjw
YE499VR+8IMfMGfOHC644AI+9alPATB16lQ++clP8qc//Wnt4WMlSdVlwDfApptuypw5c5g+fTrD
hg1j0qRJXHrppR0uM3HiRDbeeGMAjjvuOK699lqgOJ/6Mccc85b5J02axFVXXQXAjBkzmDRpEitX
ruR3v/sdxx57LOPHj+e0005jyZLivD6//e1vOf7444Hi1LKSpGqr/D74vtLU1MSECROYMGECu+66
K5dddtmbTstae0pWgE022WTt9e22244tt9yS+++/n6uuuoqLLrroLeufOHEiZ511Fs899xxz5szh
4IMPZtWqVWy22WbMnTu3zZpan81OklRdtuAb4KGHHuLhhx9ee3vu3LnssMMOjBo1ijlz5gBw3XXX
dbiOSZMm8e1vf5sXX3yR3Xbb7S33b7rppuy1115MnTqVo446iqamJt7+9rczevRorrnmGqA4B/u8
efMA2H///d90allJUrUZ8A2wcuVKTjzxRMaMGcNuu+3GggULOPvss5k2bRpTp06lubmZpqamDtdx
zDHHMGPGDI477rh255k0aRI//elPmTRp0tppl19+OZdccgnjxo1j7Nix/Pznxbl8vve97/GjH/2I
XXfdlcWLF/fMA5Uk9Vu9drrYRvB0sdXj/0/rvfVlV9oAzp6+1ueni5UkSX3HgJckqYIMeEmSKqiS
AT+QxxWsz/y/SVLPqVzADxkyhOXLlxsWA0xmsnz5coYMGdLXpUhSJVTuQDcjRoxg0aJFLFu2rK9L
0ToaMmQII0aM6OsyJKkSKhfwgwcPZvTo0X1dhiRJfapyXfSSJMmAlySpkgx4SZIqyICXJKmCDHhJ
kirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIq
yICXJKmCDHhJkirIgJckqYIMeEmSKsiAlySpggx4SZIqyICXJKmCDHhJkirIgJckqYIaFvARMTIi
bo+IBRExPyKmltPPjojFETG3vBxRs8yZEfFIRDwUEYc1qjZJkqpuUAPX/Rrwhcy8LyKGAnMi4pby
vv+VmRfUzhwRY4DJwFhgW+DWiHhXZq5pYI2SJFVSw1rwmbkkM+8rr68AHgC262CRo4EZmflqZj4O
PALs3aj6JEmqsl7ZBx8Ro4DdgVnlpM9GxP0R8ZOI2Lycth2wsGaxRbTxhSAiTo2I2RExe9myZQ2s
WpKkgavhAR8RmwLXAf+cmS8BPwZ2BMYDS4DvrMv6MnN6ZjZnZvOwYcN6vF5JkqqgoQEfEYMpwv3y
zPwvgMx8JjPXZObrwMW80Q2/GBhZs/iIcpokSVpHjRxFH8AlwAOZ+d2a6cNrZvsw8Ofy+kxgckRs
FBGjgZ2AextVnyRJVdbIUfT7A1OAP0XE3HLaWcDxETEeSOAJ4DSAzJwfEVcDCyhG4H/aEfSSJHVN
wwI+M38DRBt33dTBMucC5zaqJkmS1hceyU6SpAoy4CVJqiADXpKkCjLgJUmqIANekqQKMuAlSaog
A16SpAoy4CVJqiADXpKkCjLgJUmqIANekqQKMuAlSaogA16SpAoy4CVJqiADXpKkCjLgJUmqIANe
kqQKMuAlSaogA16SpAoy4CVJqiADXpKkCjLgJUmqIANekqQKMuAlSaogA16SpAoy4CVJqiADXpKk
CjLgJUmqIANekqQKMuAlSaogA16SpAoy4CVJqiADXpKkCjLgJUmqIANekqQK6jTgI2KTiNigvP6u
iJgYEYMbX5okSeqqelrwdwFDImI74GZgCnBpI4uSJEndU0/AR2b+FfgIcGFmHguMbWxZkiSpO+oK
+Ih4D3ACcGM5ralxJUmSpO6qJ+CnAmcCP8vM+RGxI3B7Y8uSJEndMaijOyOiCZiYmRNbpmXmY8Dn
Gl2YJEnqug5b8Jm5Bjigl2qRJEk9pJ4u+j9GxMyImBIRH2m5dLZQRIyMiNsjYkFEzI+IqeX0LSLi
loh4uPy7ec0yZ0bEIxHxUEQc1o3HJUnSeq3DLvrSEGA5cHDNtAT+q5PlXgO+kJn3RcRQYE5E3AKc
BNyWmedFxBnAGcCXImIMMJlihP62wK0R8a6yF0GSJK2DTgM+M0/uyoozcwmwpLy+IiIeALYDjgYm
lLNdBtwBfKmcPiMzXwUej4hHgL2Be7qyfUmS1mf1HMnuXRFxW0T8uby9W0R8ZV02EhGjgN2BWcA2
ZfgDPA1sU17fDlhYs9iicpokSVpH9eyDv5jiZ3KrATLzfoqu9LpExKbAdcA/Z+ZLtfdlZlJ099ct
Ik6NiNkRMXvZsmXrsqgkSeuNegL+bZl5b6tpr9Wz8vKY9dcBl2dmyz77ZyJieHn/cGBpOX0xMLJm
8RHltDfJzOmZ2ZyZzcOGDaunDEmS1jv1BPyzEfFOypZ2RBxDuW+9IxERwCXAA5n53Zq7ZgInltdP
BH5eM31yRGwUEaOBnYDWXywkSVId6hlF/2lgOvD3EbEYeBz4WB3L7U9xYpo/RcTcctpZwHnA1RHx
ceAvwHEA5VHyrgYWUPQQfNoR9JIkdU0Uu8HrmDFiE2CDzFzR2JLq19zcnLNnz+7rMiSp50T0dQW9
o87s0VtFxJzMbO5svk5b8BHx+Va3AV4E5mTm3DYXkiRJfaqeffDNwOkUP1nbDjgNOBy4OCL+pYG1
SZKkLqpnH/wIYI/MXAkQEdMoTht7EDAH+HbjypMkSV1RTwt+a+DVmturKQ5W83Kr6ZIkqZ+opwV/
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
gg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>We can see that passengers of the higher classes, 1 and 2, were more likely to survive. This effect is much more prevalent in females than males. We'll want to drill down on passengers with pclass 1 and 2 to see if we can find additional features to sort out the relatively few fatalities in these groups.</p>
<p>Note: Normalizing the data could be worthwhile here to not be misled by the visualizations.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[30]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="c1"># Separating out fatalities from Pclass 1 and 2</span>
<span class="n">vs</span><span class="o">.</span><span class="n">survival_stats</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">outcomes</span><span class="p">,</span> <span class="s1">&#39;Age&#39;</span><span class="p">,</span> <span class="p">[</span><span class="s2">&quot;Pclass &lt; 3&quot;</span><span class="p">])</span>
<span class="n">vs</span><span class="o">.</span><span class="n">survival_stats</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">outcomes</span><span class="p">,</span> <span class="s1">&#39;Age&#39;</span><span class="p">,</span> <span class="p">[</span><span class="s2">&quot;Pclass &lt; 3&quot;</span><span class="p">,</span> <span class="s2">&quot;Sex == &#39;male&#39;&quot;</span><span class="p">])</span>
<span class="n">vs</span><span class="o">.</span><span class="n">survival_stats</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">outcomes</span><span class="p">,</span> <span class="s1">&#39;Age&#39;</span><span class="p">,</span> <span class="p">[</span><span class="s2">&quot;Pclass &lt; 3&quot;</span><span class="p">,</span> <span class="s2">&quot;Sex == &#39;female&#39;&quot;</span><span class="p">])</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
Vjfi5+DBg/nKV77CqFGj2GuvvXj22WcBeOqppzjwwAPZZZddOOigg3jmmWf47W9/y7Rp0/jiF7/I
6NGjefzxx99U1jXXXMNOO+3EqFGjOOCAAwC49NJL+exnP7tqnbFjx3LXXXet2vcXvvAFRo0axTe/
+U2OOeaYVevV1qX56MJpp53GD3/4w1XrnHPOOXz7298G4Pzzz2ePPfZgl1124eyzz+7K09ouE7ok
aY3bbrvtWLlyJYsXv/lCpnPPPZf99tuPRx55hA9+8IM888wzrW6/fPly9tprL2bNmsUBBxzAJZdc
AsDnPvc5Jk6cyIMPPsgJJ5zAKaecwj777MO4ceM4//zzmTlzJu94xzveVNZXv/pVbr31VmbNmsW0
adPajX358uXsueeezJo1i9NOO43777+f5cuXA3DVVVdx3HHHvWn98ePHc/XVV6+avvrqqxk/fjy3
3XYbc+fO5YEHHmDmzJnMmDGDe+65p/0nr5NM6JKkbnPPPffwkY98BIDDDz+cjTfeuNX11l133VUt
4d13352nnnoKgPvuu48Pf/jDAEyYMIFf//rX7e5z33335aMf/SiXXHIJK1eubHf9fv368c///M8A
9O/fn8MOO4wbbriB1157jZtuuokjjzzyTevvuuuuLF68mD//+c/MmjWLjTfemG222YbbbruN2267
jV133ZXddtuNRx99lLlz57a7/87yHLokaY174okn6NevH1tssQVz5szp8PYDBgxY1QO8X79+vPba
a52O5aKLLuL+++/npptuYvfdd2fGjBn0799/Vac94E2Xjg0cOPBN582PO+44fvCDH7DJJpvQ1NTE
Bhts8JZ9HHPMMVx77bUsWrSI8ePHA8V15qeffjqT1nSfhtUwoUtdMOmG7vmg9pSLj2i/M5TU0pIl
Szj55JP57Gc/+5bLsg444ACuuOIKzjzzTG655RZeeKHNwTbfYp999mHq1KlMmDCByy+/nP333x+A
DTbYgGXLlrW6zeOPP86ee+7JnnvuyS233MK8efMYPnw4F154Ia+//joLFizggQceWO0+3/ve9/Kx
j32MSy655C2H25uNHz+eT37ykzz33HPcfffdABx66KGcddZZnHDCCQwePJgFCxYwYMAAtthiiw7V
uV4mdElSl/31r39l9OjRrFixgv79+zNhwgQ+//nPv2W9s88+m+OPP56RI0eyzz77MGzYsA7t5/vf
/z4nnngi559/Pptvvjk//elPgaIV/clPfpLvfe97XHvttW86j/7FL36RuXPnkpkcdNBBjBo1CoAR
I0aw4447ssMOO7Dbbrutdp/9+vVj7NixXHrppUyZMqXVdUaOHMmyZcvYeuutGTJkCACHHHIIc+bM
Ye+99waKznaXXXZZwxJ6rK6HYW/S1NSUjoeu3sgWunqDOXPmsMMOO/R0GOqk1l6/iJiRmR261s9O
cZIkVYAJXZKkCjChS5JUASZ0SZIqwIQuSVIFmNAlSaoAE7okaY34+te/zsiRI9lll10YPXo0999/
f5fLnDZtGuedd94aiK64DrzKvLGMJFXMmr4/Qj33I7jvvvu48cYb+cMf/sB6663Hc889x9///ve6
yn/ttdfo37/1dDRu3DjGjRvXoXjXVrbQJUldtnDhQjbbbDPWW289ADbbbDO22mqrVUOMAkyfPp0x
Y8YAxRCjEyZMYN9992XChAnstddePPLII6vKGzNmDNOnT181zOlLL73Etttuu+r+68uXL2ebbbZh
xYoVPP744xx22GHsvvvu7L///jz66KMAPPnkk+y9997svPPOnHnmmd34bPQME7okqcsOOeQQ5s2b
xzvf+U4+/elPr7qfeVtmz57Nr371K6688so3DUG6cOFCFi5cSFPTGzdK23DDDRk9evSqcm+88UYO
PfRQBgwYwEknncT3v/99ZsyYwbe//W0+/elPA3DqqafyqU99ioceemjV7VirzIQuSeqywYMHM2PG
DCZPnszmm2/O+PHjufTSS9vcZty4cQwaNAiAY489lmuvvRYoxhM/+uij37L++PHjueqqqwCYOnUq
48eP55VXXuG3v/0txxxzDKNHj2bSpEksXLgQgN/85jccf/zxQDHUatV5Dl2StEb069ePMWPGMGbM
GHbeeWemTJnypmFKa4coBVh//fVXPd56663ZdNNNefDBB7nqqqu46KKL3lL+uHHjOOOMM3j++eeZ
MWMGBx54IMuXL2ejjTZi5syZrcbUcrS3KrOFLknqsscee4y5c+eump45cybbbrstw4cPZ8aMGQD8
7Gc/a7OM8ePH861vfYuXXnqJXXbZ5S3LBw8ezB577MGpp57K2LFj6devH29/+9sZMWIE11xzDVCM
QT5r1iwA9t13X6ZOnQrA5Zdfvkbq2ZuZ0CVJXfbKK68wceJEdtxxR3bZZRdmz57NOeecw9lnn82p
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
wIQuSVIF/H+OS2iLAV1Q8QAAAABJRU5ErkJggg==
"
>
</div>

</div>

<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
l9nX9ddfzw477MDgwYMZNmwYAFdccQWf+9znlq4zYsQI7rvvvqXHPu200xg8eDDf/OY3GTVq1NL1
asvSdHbh9NNP54c//OHSdc4991wuuugiAC688EJ22203dtppJ84555yV+be2q1MSembel5kjyufz
MvOAzHxPZh6Yma90RgySpM6zzTbbsGTJEubMWfaq6nnnnce+++7Lk08+yUc/+lFeeOGFFrdftGgR
e+65J1OmTGHYsGFcfvnlAJxyyikce+yxPPbYYxxzzDGceuqp7L333owcOZILL7yQyZMn8653vWuZ
fX31q1/lzjvvZMqUKdx8883txr5o0SL22GMPpkyZwumnn87DDz/MokWLALj22ms58sgjl1l/9OjR
XHfddUunr7vuOkaPHs1dd93FtGnTeOSRR5g8eTKTJk3igQceaP+ft4LsKU6S1GkeeOABPvGJTwBw
2GGHscEGLfcttuaaay6tCe+6665Mnz4dgIceeoijjz4agDFjxvDggw+2e8x99tmH4447jssvv5wl
S5a0u36vXr34l3/5FwB69+7NIYccwi233MKbb77JbbfdxuGHH77M+jvvvDNz5szhL3/5C1OmTGGD
DTZgiy224K677uKuu+5i5513ZpddduHpp59m2rRp7R5/RfWIwVkkST3Lc889R69evdhkk02YOnVq
h7fv06fP0hbgvXr14s0331zhWC699FIefvhhbrvtNnbddVcmTZpE7969lzbaA5a5daxv377LXDc/
8sgj+cEPfsCGG27I0KFDWXfddZc7xqhRo7jhhht46aWXGD16NFDcZ37GGWcwdlW3aWiFCV1aGZ30
Qe0ydTSGkpqbO3cuJ598Mp/73OeWuy1r2LBhXHXVVZx11lnccccdvPrqqx3a9957780111zDmDFj
uPLKK9lvv/0AWHfddVm4cGGL2zz77LPsscce7LHHHtxxxx3MmDGDQYMGcckll/DWW2/x4osv8sgj
j7R6zA984AN88pOf5PLLL1/udHuT0aNHc+KJJ/Lyyy9z//33A3DwwQdz9tlnc8wxx9CvXz9efPFF
+vTpwyabbNKhMtfLhC5JWml/+9vfGDJkCIsXL6Z3796MGTOGL3zhC8utd84553DUUUex/fbbs/fe
e7Plllt26Djf//73Of7447nwwgvp378/P/3pT4GiFn3iiSfyve99jxtuuGGZ6+hf/OIXmTZtGpnJ
AQccwODBgwHYeuut2W677dh2223ZZZddWj1mr169GDFiBFdccQUTJkxocZ3tt9+ehQsXsvnmmzNg
wAAADjroIKZOncpee+0FFI3tfv7znzcsoUdrLQy7k6FDh6bjoatbsoaubmDq1Klsu+22XR2GVlBL
r19ETMrMDt3rZ6M4SZIqwIQuSVIFmNAlSaoAE7okSRVgQpckqQJM6JIkVYAJXZK0Snz9619n++23
Z6eddmLIkCE8/PDDK73Pm2++mQsuWDVjePXr12+V7Ke7smMZSaqYsbes2v4RLvtw+/0RPPTQQ9x6
6608+uijrLXWWrz88sv84x//qGv/b775Jr17t5yORo4cyciRIzsU7+rKGrokaaXNmjWLjTfemLXW
WguAjTfemM0222zpEKMAEydOZPjw4UAxxOiYMWPYZ599GDNmDHvuuSdPPvnk0v0NHz6ciRMnLh3m
dMGCBWy11VZL+19ftGgRW2yxBYsXL+bZZ5/lkEMOYdddd2W//fbj6aefBuD5559nr732Yscdd+Ss
s87qxP9G1zChS5JW2kEHHcSMGTN473vfy2c+85ml/Zm35amnnuI3v/kNV1999TJDkM6aNYtZs2Yx
dOjbHaWtt956DBkyZOl+b731Vg4++GD69OnDSSedxPe//30mTZrERRddxGc+8xkAxo0bx6c//Wke
f/zxpd2xVpkJXZK00vr168ekSZMYP348/fv3Z/To0VxxxRVtbjNy5EjWXnttAD7+8Y9zww03AMV4
4kccccRy648ePZprr70WgGuuuYbRo0fz+uuv8/vf/55Ro0YxZMgQxo4dy6xZswD43e9+x1FHHQUU
Q61WndfQJUmrRK9evRg+fDjDhw9nxx13ZMKECcsMU1o7RCnAOuuss/T55ptvzkYbbcRjjz3Gtdde
y6WXXrrc/keOHMmZZ57JK6+8wqRJk9h///1ZtGgR66+/PpMnT24xpuajvVWZNXRJ0kp75plnmDZt
2tLpyZMns9VWWzFo0CAmTZoEwI033tjmPkaPHs23v/1tFixYwE477bTc8n79+rHbbrsxbtw4RowY
Qa9evXjnO9/J1ltvzfXXXw8UY5BPmTIFgH322YdrrrkGgCuvvHKVlLM7s4auxqv6iGSSeP311znl
lFOYP38+vXv35t3vfjfjx49n6tSpnHDCCZx99tlLG8S15ogjjmDcuHGcffbZra4zevRoRo0axX33
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
QmCC
"
>
</div>

</div>

<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
3nvvzaRJkzj33HOZM2cO22+//Vvm9dWvfpWbb76ZuXPncu2113ZZ+4oVK9hjjz2YO3cup5xyCvfd
dx8rVqwA4PLLL+eYY455y/iTJ0/miiuuWH3/iiuuYPLkydxyyy0sWLCA+++/nzlz5jB79mzuuuuu
rp+8HjLQJUl95q677uLjH/84AIceeigbb7xxu+Otu+66q3vCu+22G08++SQA9957Lx/72McAmDJl
Cr/61a+6XOY+++zDJz7xCS6++GJWrVrV5fgtLS387d/+LQCDBg3ikEMO4brrruP111/nhhtu4PDD
D3/L+LvssgtLlizhj3/8I3PnzmXjjTdm66235pZbbuGWW25hl112Ydddd+WRRx5hwYIFXS6/p9yG
Lkla4x5//HFaWlrYfPPNmT9/frenHzx48Oo9wFtaWnj99dd7XMsFF1zAfffdxw033MBuu+3G7Nmz
GTRo0Oqd9oC3HDo2ZMiQt2w3P+aYY/j+97/PJptswvjx49lwww3ftoyjjjqKq666imeeeYbJkycD
xXHmp556KtPW9D4NHTDQpQFs2nV980UwUF14WNc7Y2ngWbp0KSeddBKf+9zn3nZY1v77789PfvIT
Tj/9dG666SZeeOGFbs177733ZubMmUyZMoXLLruM/fbbD4ANN9yQ5cuXtzvNY489xh577MEee+zB
TTfdxMKFCxk5ciTnn38+b7zxBk8//TT3339/h8t8//vfz9///d9z8cUXv211e6vJkydzwgkn8Nxz
z3HnnXcCcPDBB3PGGWdw3HHHMXToUJ5++mkGDx7M5ptv3q0218tAlyT12quvvsq4ceNYuXIlgwYN
YsqUKXzhC19423hnnnkmxx57LKNHj2bvvfdmm2226dZyvve973H88cdz7rnnMmzYMH784x8DRS/6
hBNO4Lvf/S5XXXXVW7ajf+lLX2LBggVkJgceeCBjx44FYNSoUey4447ssMMO7Lrrrh0us6WlhYkT
J3LJJZcwY8aMdscZPXo0y5cvZ6uttmL48OEAHHTQQcyfP5+99toLKHa2u/TSSxsW6NHRHoYDyfjx
49ProasZ2UO3h16P+fPns8MOO/R3Geqh9l6/iJidmd061s+d4iRJqgADXZKkCjDQJUmqAANdkqQK
MNAlSaoAA12SpAow0CVJa8TXv/51Ro8ezZgxYxg3bhz33Xdfr+d57bXXcs4556yB6orjwKvME8tI
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
rkJggg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[32]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="c1">#By adding in the condition age &lt; 18, we can separate out some of of </span>
<span class="c1">#the fatalities in the first and second classes, especially among males.</span>
<span class="c1">#We&#39;ll add this to our decision tree segment, and explore other variables.</span>
<span class="n">vs</span><span class="o">.</span><span class="n">survival_stats</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">outcomes</span><span class="p">,</span> <span class="s1">&#39;Parch&#39;</span><span class="p">,</span> <span class="p">[</span><span class="s2">&quot;Pclass &lt; 3&quot;</span><span class="p">,</span> <span class="s2">&quot;Age &lt; 18&quot;</span><span class="p">])</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
fpAnn3yy3elXrlzJfvvtx7x58xg3bhyXX345AJ/4xCc48cQTuf/++zn++OM566yzOOCAA5g4cSIX
Xnghc+fO5e1vf/ta8/rCF77Az372M+bNm8dNN93UZe0rV65k3333Zd68eZx99tnMmjWLlStXAnDt
tddy7LHHrjX+pEmTuO6669Y8vu6665g0aRK33347jzzyCPfccw9z585lzpw5zJw5s+sXr5sMcklS
r5k5cyYnnHACAEceeSRbbrllu+NtvPHGa3q+e++9N0888QQAd911Fx/+8IcBmDx5MnfeeWeXbR54
4IGcdNJJXH755axevbrL8Zuamvj7v/97AAYMGMARRxzBT37yE1atWsUtt9zCUUcdtdb4e+65J0uW
LOHPf/4z8+bNY8stt2THHXfk9ttv5/bbb2fPPfdkr7324qGHHuKRRx7psv3uchu5JKnHPfbYYzQ1
NbHtttuyYMGCbk8/cODANXt0NzU1sWrVqnWu5bLLLmPWrFnccsst7L333syZM4cBAwas2RkPWOsQ
sEGDBq21XfzYY4/lkksuYauttqK5uZmhQ4e+qY1jjjmGG264gaeffppJkyYBxXHi55xzDqeffvo6
114Lg1zrLS6o72EvObXrHW0kbTiWLl3KGWecwZlnnvmmw6vGjRvH97//fc4991xuu+02nnvuuW7N
+4ADDmDGjBlMnjyZq6++moMOOgiAoUOHsmLFinanefTRR9l3333Zd999ue2223jqqacYMWIE3/rW
t3jjjTdYtGgR99xzT4dtHnzwwZxyyilcfvnlb1qt3mLSpEmceuqpLFu2jF//+tcAHH744Zx33nkc
f/zxDBkyhEWLFjFw4EC23Xbbbi1zVwxySdJ6e+WVVxg7diyvv/46AwYMYPLkyXzyk59803hTp07l
uOOOY9SoURxwwAHstNNO3Wrnm9/8JieffDIXXnghw4YN43vf+x5Q9JpPPfVUvvGNb3DDDTestZ38
05/+NI888giZyaGHHsqYMWMAGDlyJLvtthu77rore+21V4dtNjU1MWHCBKZPn86VV17Z7jijRo1i
xYoV7LDDDmy33XYAHHbYYSxYsID9998fKHaiu+qqq3o8yKOjPQY3JM3Nzen1yDdc9silxlqwYAG7
7rpro8vQOmrv/YuIOZlZ0zF77uwmSVKFGeSSJFWYQS5JUoUZ5JIkVZhBLklShRnkkiRVmEEuSeoR
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
Zp6TmcMzcwRwLPDLzDyht+uQJKkv8DhySZIqbEAjG8/MO4A7GlmDJElVZo9ckqQKM8glSaowg1yS
pAozyCVJqjCDXJKkCjPIJUmqMINckqQKM8glSaowg1ySpAozyCVJqjCDXJKkCjPIJUmqMINckqQK
M8glSaowg1ySpAozyCVJqjCDXJKkCjPIJUmqMINckqQKM8glSaowg1ySpAozyCVJqjCDXJKkCjPI
JUmqMINckqQKM8glSaowg1ySpAozyCVJqjCDXJKkCjPIJUmqMINckqQKM8glSaqwXg/yiNgxIn4V
EfMj4sGImNLbNUiS1FcMaECbq4BPZeZ9ETEUmBMR/5WZ8xtQiyRJldbrPfLMXJyZ95X3VwALgB16
uw5JkvqChm4jj4gRwJ7ArHaeOy0iZkfE7KVLl/Z0w/W9SZLUSxoW5BExBPgB8I+Z+WLb5zNzWmY2
Z2bzsGHDer9ASZIqoCFBHhEDKUL86sz8YSNqkCSpL2jEXusBXAEsyMyv93b7kiT1JY3okR8ITAYO
iYi55e19DahDkqTK6/XDzzLzTsA9wiRJ6gGe2U2SpAozyCVJqjCDXJKkCjPIJUmqMINckqQKM8gl
Saowg1ySpAozyCVJqjCDXJKkCjPIJUmqMINckqQKM8glSaowg1ySpAozyCVJqjCDXJKkCjPI1fdE
1O8mSRsYg1ySpAozyCVJqjCDXJKkCjPIJUmqMINckqQKM8glSaowg1ySpAozyCVJqjCDXJKkCjPI
JUmqMINckqQKM8glSaowg1ySpAozyCVJqjCDXJKkCjPIJUmqsIYEeUQcEREPR8QfI+LsRtQgSVJf
0OtBHhFNwKXAe4HdgOMiYrferkOSpL6gET3yvwX+mJmPZeZrwAzgqAbUIUlS5TUiyHcAnmr1eGE5
TJIkdVNkZu82GHE0cERmfrR8PBnYNzPPbDPeacBp5cNdgId7tdDetQ2wrNFF9KL+tLz9aVnB5e3L
+tOyQuOXd+fMHFbLiAPqXUk7FgE7tno8vBy2lsycBkzrraIaKSJmZ2Zzo+voLf1pefvTsoLL25f1
p2WFai1vI1at3wu8MyJGRsTGwLHATQ2oQ5Kkyuv1HnlmroqIM4GfAU3AdzPzwd6uQ5KkvqARq9bJ
zFuBWxvR9gaqX2xCaKU/LW9/WlZwefuy/rSsUKHl7fWd3SRJUs/xFK2SJFWYQd5A/e1UtRHx3YhY
EhF/aHQt9RYRO0bEryJifkQ8GBFTGl1TPUXEoIi4JyLmlct7QaNrqreIaIqI30fEzY2upd4i4omI
eCAi5kbE7EbXU28RsUVE3BARD0XEgojYv9E1dcZV6w1Snqr2v4H/RXFSnHuB4zJzfkMLq6OIGAe8
BPxnZu7e6HrqKSK2A7bLzPsiYigwB/hAX31/IyKAzTLzpYgYCNwJTMnMuxtcWt1ExCeBZuAtmTmh
0fXUU0Q8ATRnZr84jjwirgR+k5nfKY+u2jQzn290XR2xR944/e5UtZk5E3i20XX0hsxcnJn3lfdX
AAvow2cwzMJL5cOB5a3P9hIiYjhwJPCdRteinhURmwPjgCsAMvO1DTnEwSBvJE9V209ExAhgT2BW
Yyupr3JV81xgCfBfmdmXl/ffgc8AbzS6kF6SwM8jYk551s2+bCSwFPheuenkOxGxWaOL6oxBLtVR
RAwBfgD8Y2a+2Oh66ikzV2fmWIqzNf5tRPTJzScRMQFYkplzGl1LL3p3+d6+F/iHcjNZXzUA2Av4
dmbuCawENuh9mAzyxqnpVLWqrnJb8Q+AqzPzh42up7eUqyF/BRzR6Frq5EBgYrndeAZwSERc1diS
6iszF5V/lwA/otg02FctBBa2WqN0A0Wwb7AM8sbxVLV9WLnz1xXAgsz8eqPrqbeIGBYRW5T3B1Ps
xPlQY6uqj8w8JzOHZ+YIiu/tLzPzhAaXVTcRsVm5wyblKubDgD575ElmPg08FRG7lIMOBTbonVQb
cmY39c9T1UbENcB4YJuIWAhMzcwrGltV3RwITAYeKLcbA3yuPKthX7QdcGV5NMZGwHWZ2ecPy+on
3gr8qPhtygDg+5n508aWVHefAK4uO1mPASc3uJ5OefiZJEkV5qp1SZIqzCCXJKnCDHJJkirMIJck
qcIMckmSKswgl/qJiFhdXr3qDxFxfURs2gPzPCkiLumJ+iStG4Nc6j9eycyx5ZXnXgPOqHXC8vhw
SRsgg1zqn34DvAMgIm4sL4bxYOsLYkTESxHxtYiYB+wfEftExO/Ka47f03K2L2D7iPhpRDwSEV9t
wLJI/ZpndpP6mYgYQHHxi5azc52Smc+Wp1a9NyJ+kJnLgc2AWZn5qfIMVw8BkzLz3oh4C/BKOf1Y
iqu7/QV4OCK+mZlPIalXGORS/zG41elif0N5vWXgrIj4YHl/R+CdwHJgNcVFXwB2ARZn5r0ALVdy
K0/b+YvMfKF8PB/YmbUv0Supjgxyqf94pbwU5RoRMR54D7B/Zr4cEXcAg8qnX83M1TXM9y+t7q/G
/ytSr3IbudS/bQ48V4b43wD7dTDew8B2EbEPQEQMLVfRS2owv4hS//ZT4IyIWEAR1ne3N1JmvhYR
k4BvltvSX6HoyUtqMK9+JklShblqXZKkCjPIJUmqMINckqQKM8glSaowg1ySpAozyCVJqjCDXJKk
CjPIJUmqsP8PNV7FPvbB7gMAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Interestingly, having a parent or child on board increases the probability of survival here. 
This is likely because the segment we are looking at is much more likely to be a child than a parent. It makes sense that having a parent present (Parch &gt; 0) incrases the probability of survival . We'll add Parch &gt; 0 to our decision tree segment.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>After exploring the survival statistics visualization, fill in the missing code below so that the function will make your prediction.<br>
Make sure to keep track of the various features and conditions you tried before arriving at your final prediction model.<br>
<strong>Hint:</strong> You can start your implementation of this function using the prediction code you wrote earlier from <code>predictions_2</code>.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[23]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">def</span> <span class="nf">predictions_3</span><span class="p">(</span><span class="n">data</span><span class="p">):</span>
    <span class="sd">&quot;&quot;&quot; Model with multiple features. Makes a prediction with an accuracy of at least 80%. &quot;&quot;&quot;</span>
    
    <span class="n">predictions</span> <span class="o">=</span> <span class="p">[]</span>
    <span class="k">for</span> <span class="n">_</span><span class="p">,</span> <span class="n">passenger</span> <span class="ow">in</span> <span class="n">data</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
        
        <span class="c1"># Remove the &#39;pass&#39; statement below </span>
        <span class="c1"># and write your prediction conditions here</span>
        <span class="k">if</span> <span class="n">passenger</span><span class="p">[</span><span class="s1">&#39;Sex&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s1">&#39;female&#39;</span> <span class="ow">or</span> <span class="n">passenger</span><span class="p">[</span><span class="s1">&#39;Age&#39;</span><span class="p">]</span> <span class="o">&lt;</span> <span class="mi">18</span> <span class="ow">and</span> <span class="n">passenger</span><span class="p">[</span><span class="s1">&#39;Pclass&#39;</span><span class="p">]</span> <span class="ow">in</span> <span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">)</span> <span class="ow">and</span> <span class="n">passenger</span><span class="p">[</span><span class="s1">&#39;Parch&#39;</span><span class="p">]</span> <span class="o">&gt;</span><span class="mi">0</span><span class="p">:</span>
            <span class="n">predictions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>
        <span class="k">else</span><span class="p">:</span>
            <span class="n">predictions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
    
    <span class="c1"># Return our predictions</span>
    <span class="k">return</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">predictions</span><span class="p">)</span>

<span class="c1"># Make the predictions</span>
<span class="n">predictions</span> <span class="o">=</span> <span class="n">predictions_3</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Question-4">Question 4<a class="anchor-link" href="#Question-4">&#182;</a></h3><p><em>Describe the steps you took to implement the final prediction model so that it got an accuracy of at least 80%. What features did you look at? Were certain features more informative than others? Which conditions did you use to split the survival outcomes in the data? How accurate are your predictions?</em><br>
<strong>Hint:</strong> Run the code cell below to see the accuracy of your predictions.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[24]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython2"><pre><span></span><span class="k">print</span> <span class="n">accuracy_score</span><span class="p">(</span><span class="n">outcomes</span><span class="p">,</span> <span class="n">predictions</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">
<div class="prompt"></div>

<div class="output_subarea output_stream output_stdout output_text">
<pre>Predictions have an accuracy of 80.13%.
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>Answer</strong>: To add a decision node to the tree, I started off by exploring data based on intuitions. once I found a signifcant pattern - that passengers in classes 1,2 were most likely to survive - I added that as a rule and tested the accuracy. When I found that this was not enough to boost the accuracy, I held "Pclass &lt; 3" constant and repeated the process, exploring new variables, adding them to the segment, and retesting. I was able to genereate a model where predictions have an accuracy of 80.13%.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Conclusion">Conclusion<a class="anchor-link" href="#Conclusion">&#182;</a></h1><p>After several iterations of exploring and conditioning on the data, you have built a useful algorithm for predicting the survival of each passenger aboard the RMS Titanic. The technique applied in this project is a manual implementation of a simple machine learning model, the <em>decision tree</em>. A decision tree splits a set of data into smaller and smaller groups (called <em>nodes</em>), by one feature at a time. Each time a subset of the data is split, our predictions become more accurate if each of the resulting subgroups are more homogeneous (contain similar labels) than before. The advantage of having a computer do things for us is that it will be more exhaustive and more precise than our manual exploration above. <a href="http://www.r2d3.us/visual-intro-to-machine-learning-part-1/">This link</a> provides another introduction into machine learning using a decision tree.</p>
<p>A decision tree is just one of many models that come from <em>supervised learning</em>. In supervised learning, we attempt to use features of the data to predict or model things with objective outcome labels. That is to say, each of our data points has a known outcome value, such as a categorical, discrete label like <code>'Survived'</code>, or a numerical, continuous value like predicting the price of a house.</p>
<h3 id="Question-5">Question 5<a class="anchor-link" href="#Question-5">&#182;</a></h3><p><em>Think of a real-world scenario where supervised learning could be applied. What would be the outcome variable that you are trying to predict? Name two features about the data used in this scenario that might be helpful for making the predictions.</em></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>Answer</strong>: A scenario where supervised learning could be useful is predicting purchasing behavior among users of a freemium website. The variable we would try to predict would be a class, purchased or did not purchase. Two features that would be helpful in predicting this class would be "number of logins", a continuous integer variable, and "signed up for a free trial", a boolean variable. I would predict that number of logins would have a significant positive correlation with purchasing behavior, and engaging in a free trial of the premium offering would also increase the probability of purchasing.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<blockquote><p><strong>Note</strong>: Once you have completed all of the code implementations and successfully answered each question above, you may finalize your work by exporting the iPython Notebook as an HTML document. You can do this by using the menu above and navigating to<br>
<strong>File -&gt; Download as -&gt; HTML (.html)</strong>. Include the finished document along with this notebook as your submission.</p>
</blockquote>

</div>
</div>
</div>
    </div>
  </div>
</body>

 


</html>
