求图形面积
测试了正方形，圆形，三角形的面积

<!DOCTYPE html>
<html>

    <head>
        <meta charset="UTF-8">
        <title></title>
        <style>
            * {
                margin: 0;
                padding: 0;
            }
            
            .a {
                width: 100px;
                height: 100px;
                border-radius: 50px;
                background: red;
            }
            
            .b {
                width: 100px;
                height: 100px;
                background: blueviolet;
            }
            
            .c {
                width: 0;
                height: 0;
                border-left: 50px solid transparent;
                border-right: 50px solid transparent;
                border-bottom: 100px solid red;
            }
        </style>
    </head>

    <body>
        <div class="a"></div>
        <div class="b"></div>
        <div class="c"></div>
        <script src="js/jquery-1.9.1.min.js"></script>
        <script>
            var mj = [];

            $("div").each(function(index, item) {
                var w = $(this).width();
                var h = $(this).height();

                if($(this).css("border-radius").split("p")[0] > 0 && 2 * $(this).css("border-radius").split("p")[0] >= $(this).width()) {
                    w = $(this).width() / 2;
                    mj.push('{圆形:' + w * w * 3.14 + '}');
                }

                if(w == h && w !== 0) {
                    mj.push('{正方形:' + w * h + '}');
                }

                if(w == 0 || h == 0) {
                    w = $(this).css("border-bottom-width").split("p")[0];
                    mj.push('{三角形:' + w * w / 2 + '}');
                }
            })

            console.log(mj)
        </script>
    </body>

</html>
