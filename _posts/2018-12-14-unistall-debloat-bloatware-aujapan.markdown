---
layout: post
title:  "Hapus Aplikasi Bloatware Bawaan HP AU Japan"
date:   2018-12-14 20:15:00 +7
categories: au
tags : au xperia aplikasi
img: https://ftf.andro.plus/img/SOV35.png
---
Buat catatan lagi semata, untuk hapus aplikasi sistem bawaan rom tipe AU, yaitu dengan cara uninstall via adb shell dengan perintah <code>pm (package manager)</code> (tanpa harus root), beda dengan versi docomo yang
banyak banget aplikasi bawaan nya, au dikit dan asyiknya lagi bisa sync akun xperia like a global rom, buat yang pertahanin NFC wajib pake rom stock, dan hapusin aplikasi bawaan nya, via adb.
{% highlight shell %}
adb devices
adb shell
pm uninstall -k --user 0 com.kddi.market
{% endhighlight %}
<b>NB</b>: disini kita butuh user yak, jadi kita uninstall apl tsb via --user 0 (0=administrator)
dah gitu aja, ane pake SOV35 (Xperia XZs) di Android O, ane dah tulis nama2 packname nya nih, tinggal copas aja, buat balikin aplikasi bawaan softbank langsung factory reset aja. di sini ane hapus sekalian app pesan bawaan, pake app pesan lain yang lebih oke kaya messanging by google. <i>be carefull</i>
# AU
## priv & system app
{% highlight shell %}
pm uninstall -k --user 0 com.kddi.disasterapp
pm uninstall -k --user 0 com.kddi.android.auoneidsetting
pm uninstall -k --user 0 com.kddi.market
pm uninstall -k --user 0 com.kddi.android.au_wifi_connect2
pm uninstall -k --user 0 com.uievolution.gguide.android
pm uninstall -k --user 0 com.kddi.android.email
pm uninstall -k --user 0 com.lookout
pm uninstall -k --user 0 com.kddi.android.imp
pm uninstall -k --user 0 com.kddi.cs.app001
pm uninstall -k --user 0 com.kddi.android.cmail
pm uninstall -k --user 0 jp.netstar.familysmile
pm uninstall -k --user 0 jp.sony.spot.sp
pm uninstall -k --user 0 com.kddi.android.mamoru
pm uninstall -k --user 0 com.kddi.android.repairreceipt
pm uninstall -k --user 0 com.kddi.android.checker_android
pm uninstall -k --user 0 com.kddi.android.auhomelauncher
pm uninstall -k --user 0 com.kddi.android.easysettingwizard
pm uninstall -k --user 0 com.kddi.android.au_setting_menu
pm uninstall -k --user 0 com.kddi.android.aumanagementsystem
pm uninstall -k --user 0 com.kddi.android.ausharelink
pm uninstall -k --user 0 com.kddi.android.klop
pm uninstall -k --user 0 com.sonymobile.kddi.settings
pm uninstall -k --user 0 com.kddi.android.antijaywalk
pm uninstall -k --user 0 com.kddi.android.btdun
pm uninstall -k --user 0 com.kddi.selfcare.client
pm uninstall -k --user 0 com.gemalto.tsmproxy
pm uninstall -k --user 0 com.kddi.android.emailprov
pm uninstall -k --user 0 jp.co.optim.oru
pm uninstall -k --user 0 jp.co.fsi.fs1seg
pm uninstall -k --user 0 com.sonyericsson.android.contactpicker3
pm uninstall -k --user 0 com.felicanetworks.mfc
pm uninstall -k --user 0 com.felicanetworks.mfm
{% endhighlight %}

## optional
{% highlight shell %}
pm uninstall -k --user 0 com.sonymobile.android.externalkeyboardjp
pm uninstall -k --user 0 com.sonyericsson.textinput.chinese
pm uninstall -k --user 0 com.sonymobile.pobox
pm uninstall -k --user 0 com.sonymobile.pobox.skin.easy
pm uninstall -k --user 0 com.sonymobile.pobox.skin.standard
pm uninstall -k --user 0 com.sonymobile.pobox.skin.gummi
pm uninstall -k --user 0 com.sonymobile.pobox.skin.wood
{% endhighlight %}

## 3rd apps
{% highlight shell %}
pm uninstall -k --user 0 com.google.android.tts
pm uninstall -k --user 0 com.google.android.apps.docs.editors.sheets
pm uninstall -k --user 0 com.google.android.apps.docs.editors.slides
pm uninstall -k --user 0 com.google.android.apps.photos
pm uninstall -k --user 0 com.google.android.talk
pm uninstall -k --user 0 com.google.android.videos
pm uninstall -k --user 0 com.google.android.music
{% endhighlight %}


Versi Softbank / Docomo lihat note sebelumnya. Refrensi tutorial ane:<br/>
https://webruary.net/mobile/2017-06-09/xperia-z5-compact/<br/>
http://smartasw.com/archives/21462117.html
