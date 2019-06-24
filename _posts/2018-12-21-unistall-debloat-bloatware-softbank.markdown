---
layout: post
title:  "Hapus Aplikasi Bloatware Bawaan HP Softbank"
date:   2018-12-21 21:00:00 +7
categories: softbank
tags : softbank xperia aplikasi
img: https://ftf.andro.plus/img/601SO.png
---
Buat catatan lagi semata, untuk hapus aplikasi sistem bawaan rom softbank, yaitu dengan cara uninstall via adb shell dengan perintah <code>pm (package manager)</code> (tanpa harus root), beda dengan versi docomo yang
banyak banget aplikasi bawaan nya, sofbank dikit dan asyiknya lagi bisa sync akun xperia like a global rom, buat yang pertahanin NFC wajib pake rom stock, dan hapusin aplikasi bawaan nya, via adb.
{% highlight shell %}
adb devices
adb shell
pm uninstall -k --user 0 jp.softbank.mb.dtm
{% endhighlight %}
<b>NB</b>: disini kita butuh user yak, jadi kita uninstall apl tsb via --user 0 (0=administrator)
dah gitu aja, ane pake 601SO (Xperia XZ), ane dah tulis nama2 packname nya nih, tinggal copas aja, buat balikin aplikasi bawaan softbank langsung factory reset aja. <i>be carefull</i>
{% highlight shell %}
#Softbank
pm uninstall -k --user 0 jp.softbank.mb.ichinaviclt
pm uninstall -k --user 0 jp.sony.spot.sp
pm uninstall -k --user 0 jp.softbank.mb.parentalcontrols
pm uninstall -k --user 0 jp.softbank.mb.dmb
pm uninstall -k --user 0 jp.softbank.mb.dtm
pm uninstall -k --user 0 jp.softbank.mb.cbm
pm uninstall -k --user 0 jp.softbank.mb.tdrl
pm uninstall -k --user 0 jp.softbank.mb.manualviewer40
pm uninstall -k --user 0 jp.co.softbank.mb.pim
pm uninstall -k --user 0 jp.co.softbank.wispr.froyo
pm uninstall -k --user 0 jp.co.fsi.fs1seg
pm uninstall -k --user 0 jp.co.optim.orusoxp00
pm uninstall -k --user 0 jp.softbank.mobileid.installer
pm uninstall -k --user 0 jp.softbank.mb.mail
pm uninstall -k --user 0 jp.softbank.mb.mimamorimap
pm uninstall -k --user 0 com.felicanetworks.mfm
pm uninstall -k --user 0 com.felicanetworks.mfc
pm uninstall -k --user 0 com.mobiroo.xgen

#optional
pm uninstall -k --user 0 com.sonyericsson.textinput.chinese
pm uninstall -k --user 0 com.sonymobile.pobox
pm uninstall -k --user 0 com.sonymobile.pobox.skin.easy
pm uninstall -k --user 0 com.sonymobile.pobox.skin.standard
pm uninstall -k --user 0 com.sonymobile.pobox.skin.gummi
pm uninstall -k --user 0 com.sonymobile.pobox.skin.wood

#3rd apps
pm uninstall -k --user 0 com.spotify.music
pm uninstall -k --user 0 com.google.android.apps.docs.editors.sheets
pm uninstall -k --user 0 com.google.android.apps.docs.editors.slides
pm uninstall -k --user 0 com.google.android.apps.photos
pm uninstall -k --user 0 com.google.android.talk
pm uninstall -k --user 0 com.google.android.videos
pm uninstall -k --user 0 com.google.android.music
{% endhighlight %}

Versi Docomo lihat post sebelumnya. Refrensi tutorial ane:<br />
https://webruary.net/mobile/2017-06-09/xperia-z5-compact/<br />
http://smartasw.com/archives/21462117.html
