GMT时间格式转YYYY-MM-DD格式
```js
function GMTToStr(time) {
    let date = new Date(time)
    let result =
        date.getFullYear() +
        "-" +
        (date.getMonth() + 1 >= 10
            ? date.getMonth() + 1
            : "0" + (date.getMonth() + 1)) +
        "-" +
        (date.getDate() >= 10
            ? date.getDate()
            : "0" + date.getDate());
    return result
}
```
获取最近自定义天数的时间范围：
```js
function getRecentDays(days) {
    let date = new Date();
    // 通过时间戳计算
    let starTime = date.getTime() - days * 24 * 3600 * 1000; // 转化为时间戳
    let endTime = date.getTime();
    let startDateNs = new Date(starTime);
    let endDateNs = new Date(endTime);
    starTime =
        startDateNs.getFullYear() +
        "-" +
        (startDateNs.getMonth() + 1 >= 10
            ? startDateNs.getMonth() + 1
            : "0" + (startDateNs.getMonth() + 1)) +
        "-" +
        (startDateNs.getDate() >= 10
            ? startDateNs.getDate()
            : "0" + startDateNs.getDate());
    endTime =
        endDateNs.getFullYear() +
        "-" +
        (endDateNs.getMonth() + 1 >= 10
            ? endDateNs.getMonth() + 1
            : "0" + (endDateNs.getMonth() + 1)) +
        "-" +
        (endDateNs.getDate() >= 10
            ? endDateNs.getDate()
            : "0" + endDateNs.getDate());
    return [starTime, endTime];
}
```
时间戳转正常格式时间：
```js
function timestampToTime(timestamp) {
    let date = new Date(timestamp);
    let Y = date.getFullYear() + '-';
    let M = (date.getMonth() + 1 < 10 ? '0' + (date.getMonth() + 1) : date.getMonth() + 1) + '-';
    let D = date.getDate() + ' ';
    let h = date.getHours() + ':';
    let m = date.getMinutes() + ':';
    let s = date.getSeconds();
    return Y + M + D + h + m + s;
}
```