# JAVASCRIPT Check Client Bandwidth
##
(http://upload.wikimedia.org/wikipedia/commons/5/51/Google.png)
Size = 238 KB
```
function measureBW(cnt, cb) {
    var start = new Date().getTime();
    var bandwidth;
    var i = 0;
    (function rec() {
        var xmlHttp = new XMLHttpRequest();
        xmlHttp.open('GET', 'http://upload.wikimedia.org/wikipedia/commons/5/51/Google.png', true);

        xmlHttp.onreadystatechange = function () {
            if (xmlHttp.readyState == 4) {
                var x = new Date().getTime() - start;
                bw = Number(((238 / (x / 1000))));
                bandwidth = ((bandwidth || bw) + bw) / 2;
                i++;
              if (i < cnt) {
                start = new Date().getTime();rec();
              }
                else cb(bandwidth.toFixed(0));
            }
        };
        xmlHttp.send(null);
    })();

}

measureBW(10, function (e) {
    console.log(e);
});
```
