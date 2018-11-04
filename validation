var status, form, ers;
function checkvalidation(sender) {
    form = sender;
    valid();
    return eval(status);
}
function valid() {
    status = true;
    $(form).find('[data-validation]').removeClass('bg-error').parent().children('.error').remove();
    var ele = $(form).find('[data-validation]');
    for (var i = 0; i < ele.length; i++) {
        check(ele.eq(i));
    }
    checkTrim();
}
function check(sender) {
    var sd = sender.attr('data-validation');
    if (sender.parents('.hide').css('display') == "none" || sender.parents('.choose').find('.choosed').length > 0) 
        return;
    if (sd.indexOf("val") > -1) {
        if (sender.attr('data-error') != undefined)
            ers = 'لطفا ' + sender.attr('data-error') + ' را وارد نمایید ';
        else
            ers = sender.attr('data-custom-error');
        option.empty = ers;
        if (!val(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("email") > -1) {
        if (!validateEmail(sender)) {
            status = false;
            return;
        }
    } if (sd.indexOf("mobile") > -1) {
        if (!validateMobile(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("tel") > -1) {
        if (!validateTel(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("integer") > -1) {
        if (!validateInteger(sender)) {
            status = false;
            return;
        }

    } if (sd.indexOf("string") > -1) {
        if (!validateString(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("web") > -1) {
        if (!validateWebsite(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("url") > -1) {
        if (!validateUrl(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("equal") > -1) {
        if (!validateEqual(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("length") > -1) {
        if (!validateLength(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("nationalcode") > -1) {
        if (!validateNationalCode(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("postalcode") > -1) {
        if (!validatePostalCode(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("shaba") > -1) {
        if (!validateShaba(sender)) {
            status = false;
            return;
        }
    }
    if (sd.indexOf("date") > -1) {
        if (!validateDate(sender)) {
            status = false;
            return;
        }
    }
}
function checkTrim() {
    var ele = $(form).find('input[type="text"],input[type="password"],textarea');
    for (i = 0; i < ele.length; i++) {
        ele.eq(i).val(ele.eq(i).val().trim());
    }
}
function val(sender) {
    sender.val() == undefined ? "" : sender.val().trim();
    if (sender.val().trim() == "") {
        error(sender, option.empty);
        return false;
    } else
        return true;
}
function validateEmail(email) {
    if (email.val() != "") {
        var re = /^([\w-]+(?:\.[\w-]+)*)@((?:[\w-]+\.)*\w[\w-]{0,66})\.([a-z]{2,6}(?:\.[a-z]{2})?)$/i;
        if (re.test(email.val().trim())) {
            return true;
        } else {
            error(email, option.email);
            return false;
        }
    } else
        return true;
}
function validateMobile(mobile) {
    if (mobile.val() != "") {
        var re = /^(0|\+98)?([ ]|-|[()]){0,2}9[0-9]([ ]|-|[()]){0,2}(?:[0-9]([ ]|-|[()]){0,2}){8}$/;
        if (re.test(toEnglishNumber(mobile.val().trim()))) {
            return true;
        } else {
            error(mobile, option.mobile);
            return false;
        }
    } else
        return true;
}
function validateTel(tel) {
    if (tel.val() != "") {
        var re = /^[0][0-9]*$/;
        if (re.test(toEnglishNumber(tel.val().trim()))) {
            return true;
        } else {
            error(tel, option.tel);
            return false;
        }
    } else
        return true;
}
function validateInteger(int) {
    if (int.val() != "") {
        var re = /^\d+$/;
        if (re.test(toEnglishNumber(int.val().trim()))) {
            return true;
        } else {
            error(int, option.integer);
            return false;
        }
    } else
        return true;
}
function validateString(string) {
    if (string.val() != "") {
        var re = /^\d+$/;
        if (re.test(string.val().trim())) {
            error(string, option.string);
            return false;
        } else
            return true;
    } else
        return true;
}
function validateWebsite(web) {
    if (web.val() != "") {
        var re = /^(http\:\/\/|https\:\/\/)?([a-z0-9][a-z0-9\-]*\.)+[a-z0-9][a-z0-9\-]*$/;
        if (re.test(web.val().trim())) {
            return true;
        } else {
            error(web, option.web);
            return false;
        }
    } else
        return true;
}
function validateUrl(url) {
    if (url.val() != "") {
        var re = /^(https?):\/\/([a-zA-Z0-9.-]+(:[a-zA-Z0-9.&%$-]+)*@)*((25[0-5]|2[0-4][0-9]|1[0-9]{2}|[1-9][0-9]?)(\.(25[0-5]|2[0-4][0-9]|1[0-9]{2}|[1-9]?[0-9])){3}|([a-zA-Z0-9-]+\.)*[a-zA-Z0-9-]+\.(com|ir|edu|gov|int|mil|net|org|biz|arpa|info|name|pro|aero|coop|museum|[a-zA-Z]{2}))(:[0-9]+)*(\/($|[a-zA-Z0-9.,?'\\+&%$#=~_-]+))*$/;
        if (re.test(url.val().trim())) {
            return true;
        } else {
            error(url, option.web);
            return false;
        }
    } else
        return true;
}
function validateEqual(equal) {
    if (equal.val() != "") {
        var equ = $(form).find('[data-equal=' + equal.attr('data-equal') + ']');
        var checkEqual = true;
        for (i = 1; i < equ.length; i++) {
            if (equ.eq(0).val().trim() == equ.eq(i).val().trim())
                checkEqual = true;
            else {
                error(equal, equal.attr('data-equal-error') + ' تطابق ندارد');
                checkEqual = false;
            }
        }
        return eval(checkEqual);
    } else
        return true;
}
function validateLength(length) {
    if (length.val() != "") {
        var len = length.attr('data-len');
        if (length.val().trim().length >= len)
            return true;
        else {
            error(length, length.attr('data-error') + ' باید حداقل ' + len + ' کارکتر باشد');
            return false;
        }
    } else
        return true;
}
function validateNationalCode(code) {
    if (code.val() != "") {
        var re = /^(?!(\d)\1{9})\d{10}$/
        if (re.test(code.val().trim())) {
            var check = parseInt(code.val()[9]);
            var sum = [0, 1, 2, 3, 4, 5, 6, 7, 8]
                .map(function (x) { return parseInt(code.val()[x]) * (10 - x); })
                .reduce(function (x, y) { return x + y; }) % 11;
            if (sum < 2 && check == sum || sum >= 2 && check + sum == 11)
                return true;
            else {
                error(code, option.national);
                return false;
            }
        } else {
            error(code, option.national);
            return false;
        }
    } else
        return true;
}
function validatePostalCode(code) {
    if (code.val() != "") {
        var re = /^\d{10}$/
        if (re.test(toEnglishNumber(code.val().trim())))
            return true;
        else {
            error(code, option.postal);
            return false;
        }
    } else
        return true;
}
function validateShaba(code) {
    if (code.val() != "") {
        var re = /^\d{24}$/
        if (re.test(toEnglishNumber(code.val().trim())))
            return true;
        else {
            error(code, option.shaba);
            return false;
        }
    } else
        return true;
}
function validateGuidNumber(code) {
    if (code.val() != "") {
        var re = /^\d{11}$/
        if (re.test(code.val().trim()))
            return true;
        else {
            error(code, option.guid);
            return false;
        }
    } else
        return true;
}
function validateDate(date) {
    if (date.val() != "") {
        var ddd = new Date(date.val().trim());
        var d = ddd.getFullYear() + "/" + ((ddd.getMonth() + 1) > 9 ? (ddd.getMonth() + 1) : ("0" + (ddd.getMonth() + 1))) + "/" + (ddd.getDate() > 9 ? ddd.getDate() : "0" + ddd.getDate());
        var re = /^[0-9]{4}[/](0[1-9]|1[0-2])[/](0[1-9]|[1-2][0-9]|3[0-1])$/
        if (re.test(d)) {
            return true;
        }
        else {
            error(date, option.date);
            return false;
        }
    } else
        return true;
}
function error(er, msg) {
    er.addClass('bg-error');
    if (er.parent().children('.error').length > 0) {
        var ele = er.parent().children('.error');
        for (var i = 0; i < ele.length; i++) {
            if (ele.eq(i).text() != msg) {
                er.parent().children().last().after('<span class="error">' + msg + '</span>');
                return;
            }
        }
    }
    else
        er.parent().children().last().after('<span class="error">' + msg + '</span>');
}
function toEnglishNumber(num) {
    var englishNumbers = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "0"],
        persianNumbers = ["۱", "۲", "۳", "۴", "۵", "۶", "۷", "۸", "۹", "۰"],
         arabicNumbers = ["١", "٢", "٣", "٤", "٥", "٦", "٧", "٨", "٩", "٠"];
    for (var i = 0, numbersLen = persianNumbers.length; i < numbersLen; i++)
        num = num.replace(new RegExp(persianNumbers[i], "g"), englishNumbers[i]);
    for (var i = 0, numbersLen = arabicNumbers.length; i < numbersLen; i++)
        num = num.replace(new RegExp(arabicNumbers[i], "g"), englishNumbers[i]);
    return num;
}

var option = {
    empty: '',
    email: 'ایمیل معتبر نیست',
    mobile: 'موبایل معتبر نیست',
    tel: 'تلفن را همراه با کد شهر وارد نمایید',
    integer: ' لطفا عدد صحیح وارد نمایید',
    string: 'لطفا حروف وارد نمایید',
    web: 'آدرس اینترنتی معتبر نیست',
    national: 'کد ملی معتبر نیست',
    postal: 'کد پستی معتبر نیست',
    guid: 'شماره صنفی معتبر نیست',
    date: 'تاریخ معتبر نیست',
    shaba: 'شماره شبا معتبر نیست'
}
