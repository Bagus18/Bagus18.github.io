---
layout: post
title:  "Hapus Aplikasi Bloatware Bawaan HP Docomo"
date:   2018-10-16 21:00:00 +7
categories: docomo
tags : docomo xperia aplikasi
img: https://ftf.andro.plus/img/SO-02H.png
---
Buat catatan ane semata, untuk hapus aplikasi sistem bawaan rom docomo, yaitu dengan cara uninstall via adb shell dengan perintah
pm (package manager), untuk disable seharusnya sih bisa, yaitu dengan perintah
{% highlight shell %}pm disable {% endhighlight %}
di sini ane praktek langsung uninstall aja biar bersih sekalian, untuk pertama harus punya adb interface di pc untuk komunikasi sama
hp nya nantiw, terus debugging usb juga idupin di opsi pengembang, kalo udah, install apl Link2SD kalau ane, buat temuin nama package aplikasinya, misal namanya adalah <code>jp.dmapnavi.navi02</code>
tinggal command aja via terminal nya, kalau sucsess berarti berhasil, kalau ada 0 nya berarti tdak terinstall, kalau ga boleh, matiin dulu centangan administator perangkat.
{% highlight shell %}
adb devices
adb shell
pm uninstall -k --user 0 jp.dmapnavi.navi02
{% endhighlight %}
<b>NB</b>: disini kita butuh user yak, jadi kita uninstall apl tsb via --user 0 (0=administrator)
dah gitu aja, kalau mau hapus hati2, karena kalau salah ga bisa dibalikin lagi, ane pake SO-02H, ane ada refrensi nama2 package docomo nya nih, tinggal copas aja. <i>be carefull</i>
{% highlight shell %}
pm uninstall -k --user 0 com.google.android.apps.docs
pm uninstall -k --user 0 com.google.android.music
pm uninstall -k --user 0 com.google.android.apps.photos
pm uninstall -k --user 0 com.google.android.videos
pm uninstall -k --user 0 com.google.android.talk
pm uninstall -k --user 0 com.nttdocomo.android.atf
pm uninstall -k --user 0 com.amazon.mShop.android.shopping
pm uninstall -k --user 0 com.mcafee.vsm_android_dcm
pm uninstall -k --user 0 com.nttdocomo.android.bugreport
pm uninstall -k --user 0 com.nttdocomo.android.areamail
pm uninstall -k --user 0 com.android.bookmarkprovider
pm uninstall -k --user 0 jp.co.nttdocomo.bridgelauncher
pm uninstall -k --user 0 com.nttdocomo.android.initialization
pm uninstall -k --user 0 com.nttdocomo.android.accountwipe
pm uninstall -k --user 0 com.nttdocomo.android.pf.dcmippushaggregator
pm uninstall -k --user 0 com.nttdocomo.android.pf.dcmwappush
pm uninstall -k --user 0 jp.co.omronsoft.android.decoemojimanager_docomo
pm uninstall -k --user 0 jp.co.nttdocomo.saigaiban
pm uninstall -k --user 0 com.nttdocomo.android.felicaremotelock
pm uninstall -k --user 0 com.google.android.apps.docs.editors.docs
pm uninstall -k --user 0 com.sonymobile.pobox.skin.easy
pm uninstall -k --user 0 com.google.android.tts
pm uninstall -k --user 0 com.sonymobile.pobox.skin.gummi
pm uninstall -k --user 0 com.ipg.gguide.dcm_app.android
pm uninstall -k --user 0 com.nttdocomo.android.voicetranslation
pm uninstall -k --user 0 com.somc.so01j.manual
pm uninstall -k --user 0 com.amazon.kindle
pm uninstall -k --user 0 jp.co.lawson.activity
pm uninstall -k --user 0 jp.co.mcdonalds.android
pm uninstall -k --user 0 com.nttdocomo.android.mediaplayer
pm uninstall -k --user 0 com.felicanetworks.mfc
pm uninstall -k --user 0 com.mobileselect.somcprein
pm uninstall -k --user 0 com.nttdocomo.android.voiceeditor
pm uninstall -k --user 0 com.nttdocomo.android.remotelock
pm uninstall -k --user 0 com.felicanetworks.mfm.main
pm uninstall -k --user 0 com.felicanetworks.mfm
pm uninstall -k --user 0 com.felicanetworks.mfs
pm uninstall -k --user 0 com.nttdocomo.osaifu.tsmproxy
pm uninstall -k --user 0 com.felicanetworks.mfw.a.main
pm uninstall -k --user 0 com.felicanetworks.mfw.a.boot
pm uninstall -k --user 0 com.nttdocomo.android.devicehelp
pm uninstall -k --user 0 com.android.dialer
pm uninstall -k --user 0 com.sony.drbd.reader.other.jp
pm uninstall -k --user 0 com.nttdocomo.android.schedulememo
pm uninstall -k --user 0 com.nttdocomo.android.screenlockservice
pm uninstall -k --user 0 com.google.android.apps.docs.editors.sheets
pm uninstall -k --user 0 com.google.android.apps.docs.editors.slides
pm uninstall -k --user 0 com.sonymobile.pobox.skin.standard
pm uninstall -k --user 0 com.nttdocomo.android.phonemotion
pm uninstall -k --user 0 jp.co.fsi.fs1seg
pm uninstall -k --user 0 com.nttdocomo.android.tapandpay
pm uninstall -k --user 0 com.nttdocomo.android.toruca
pm uninstall -k --user 0 com.sonymobile.pobox.skin.wood
pm uninstall -k --user 0 com.sonyericsson.textinput.chinese
pm uninstall -k --user 0 com.sonymobile.pobox
pm uninstall -k --user 0 com.sonyericsson.androidapp.sehome
pm uninstall -k --user 0 com.nttdocomo.android.dpoint
pm uninstall -k --user 0 jp.co.nttdocomo.dbook
pm uninstall -k --user 0 com.sonymobile.deqp
pm uninstall -k --user 0 com.nttdocomo.android.store
pm uninstall -k --user 0 com.nttdocomo.android.applicationmanager
pm uninstall -k --user 0 com.nttdocomo.android.accountauthenticator
pm uninstall -k --user 0 com.nttdocomo.android.sdcardbackup
pm uninstall -k --user 0 com.nttdocomo.android.dhome
pm uninstall -k --user 0 com.nextbit.app
pm uninstall -k --user 0 com.nttdocomo.android.cloudset
pm uninstall -k --user 0 jp.co.nttdocomo.lcsapp
pm uninstall -k --user 0 jp.co.nttdocomo.lcsappsub
pm uninstall -k --user 0 jp.co.nttdocomo.carriermail
pm uninstall -k --user 0 com.android.contacts
pm uninstall -k --user 0 com.nttdocomo.android.docomoset
pm uninstall -k --user 0 com.nttdocomo.android.idmanager
pm uninstall -k --user 0 com.nttdocomo.android.dmenu2
pm uninstall -k --user 0 jp.id_credit_sp.android
pm uninstall -k --user 0 com.nttdocomo.android.iconcier
pm uninstall -k --user 0 com.nttdocomo.android.iconcier_contents
pm uninstall -k --user 0 jp.co.nttdocomo.anshinmode
pm uninstall -k --user 0 com.nttdocomo.android.mascot
pm uninstall -k --user 0 com.nttdocomo.android.databackup
pm uninstall -k --user 0 com.nttdocomo.android.cloudstorageservice
pm uninstall -k --user 0 com.nttdocomo.android.dcmvoicerecognition
pm uninstall -k --user 0 com.nttdocomo.android.photocollection
pm uninstall -k --user 0 com.nttdocomo.android.moneyrecord
pm uninstall -k --user 0 jp.dmapnavi.navi02
pm uninstall -k --user 0 com.rsupport.rs.activity.ntt
pm uninstall -k --user 0 com.nttdocomo.android.ictrw
pm uninstall -k --user 0 com.nttdocomo.android.wipe
{% endhighlight %}


Untuk Xperia X Compact (Kredit M Rozy Ardiansyah)
{% highlight shell %}
pm uninstall -k --user 0 com.mobileselect.somcprein
pm uninstall -k --user 0 jp.co.nttdocomo.anshinmode
pm uninstall -k --user 0 jp.co.fsi.fs1seg
pm uninstall -k --user 0 jp.dmapnavi.navi02
pm uninstall -k --user 0 com.sony.drbd.reader.other.jp
pm uninstall -k --user 0 com.rsupport.rs.activity.ntt
pm uninstall -k --user 0 com.mcafee.vsm_android_dcm
pm uninstall -k --user 0 com.nttdocomo.android.areamail
pm uninstall -k --user 0 com.nttdocomo.android.bugreport
pm uninstall -k --user 0 com.nttdocomo.android.atf
pm uninstall -k --user 0 jp.co.nttdocomo.dbook
pm uninstall -k --user 0 com.nttdocomo.android.accountwipe
pm uninstall -k --user 0 com.nttdocomo.android.pf.dcmippushaggregator
pm uninstall -k --user 0 com.ntt.docomo.android.pf.dcmwappush
pm uninstall -k --user 0 jp.co.omronsoft.android.decoemojimanager_docomo
pm uninstall -k --user 0 jp.co.nttdocomo.saigaiban
pm uninstall -k --user 0 com.nttdocomo.android.store
pm uninstall -k --user 0 com.nttdocomo.android.applicationmanager
pm uninstall -k --user 0 com.nttdocomo.android.applicationmanager.RecommendActivity
pm uninstall -k --user 0 com.nttdocomo.android.accountauthenticator
pm uninstall -k --user 0 com.nttdocomo.android.sdcardbackup
pm uninstall -k --user 0 com.nttdocomo.android.sdcardbackup.view.LaunchActivity
pm uninstall -k --user 0 com.nttdocomo.android.cloudset
pm uninstall -k --user 0 com.nttdocomo.android.initialization
pm uninstall -k --user 0 com.nttdocomo.android.lac
pm uninstall -k --user 0 com.nttdocomo.android.dhome
pm uninstall -k --user 0 com.nextbit.app
pm uninstall -k --user 0 jp.co.nttdocomo.lcsapp
pm uninstall -k --user 0 jp.co.nttdocomo.lcsappsub
pm uninstall -k --user 0 jp.co.nttdocomo.carriermail
pm uninstall -k --user 0 com.android.contacts
pm uninstall -k --user 0 com.nttdocomo.android.docomoset
pm uninstall -k --user 0 com.nttdocomo.android.dpoint
pm uninstall -k --user 0 com.google.android.apps.docs
pm uninstall -k --user 0 com.nttdocomo.android.idmanager
pm uninstall -k --user 0 com.nttdocomo.android.dmenu2
pm uninstall -k --user 0 com.nttdocomo.android.docomo_market.ui.StartupActivity
pm uninstall -k --user 0 com.sonymobile.pobox.skin.easy
pm uninstall -k --user 0 com.google.android.apps.photos
pm uninstall -k --user 0 com.google.android.videos
pm uninstall -k --user 0 com.google.android.music
pm uninstall -k --user 0 com.sonymobile.pobox.skin.gummi
pm uninstall -k --user 0 com.ipg.gguide.dcm_app.android
pm uninstall -k --user 0 com.nttdocomo.android.voicetranslation
pm uninstall -k --user 0 com.google.android.talk
pm uninstall -k --user 0 com.google.android.talk.SigningInActivity
pm uninstall -k --user 0 jp.id_credit_sp.android
pm uninstall -k --user 0 com.instagram.android
pm uninstall -k --user 0 com.somc.so02j.manual
pm uninstall -k --user 0 com.nttdocomo.android.iconcier
pm uninstall -k --user 0 com.nttdocomo.android.iconcier_contents
pm uninstall -k --user 0 com.amazon.kindle
pm uninstall -k --user 0 jp.co.lawson.activity
pm uninstall -k --user 0 com.sonymobile.lifelog
pm uninstall -k --user 0 jp.co.mcdonalds.android
pm uninstall -k --user 0 com.nttdocomo.android.mediaplayer
pm uninstall -k --user 0 com.facebook.orca
pm uninstall -k --user 0 com.nttdocomo.android.voiceeditor
pm uninstall -k --user 0 com.sony.nfx.app.sfrc
pm uninstall -k --user 0 com.nttdocomo.osaifu.tsmproxy
pm uninstall -k --user 0 com.sonyericsson.updatecenter
pm uninstall -k --user 0 com.sonymobile.androidapp.cameraaddon.stickercreator
pm uninstall -k --user 0 com.android.dialer
pm uninstall -k --user 0 com.nttdocomo.android.socialphonebook
pm uninstall -k --user 0 com.nttdocomo.android.wipe
pm uninstall -k --user 0 com.rsupport.rsperm.ntt
pm uninstall -k --user 0 com.nttdocomo.android.rwpushcontroller
pm uninstall -k --user 0 com.nttdocomo.android.schedulememo
pm uninstall -k --user 0 com.nttdocomo.android.screenlockservice
pm uninstall -k --user 0 com.nttdocomo.android.settings.lac
pm uninstall -k --user 0 com.google.android.apps.docs.editors.slides
pm uninstall -k --user 0 com.google.android.apps.docs.editors.sheets
pm uninstall -k --user 0 com.nttdocomo.android.phonemotion
pm uninstall -k --user 0 com.nttdocomo.android.toruca
pm uninstall -k --user 0 com.twitter.android
pm uninstall -k --user 0 com.sonymobile.pobox.skin.wood
pm uninstall -k --user 0 com.google.android.youtube
pm uninstall -k --user 0 com.sonyericsson.androidapp.sehome
pm uninstall -k --user 0 com.felicanetworks.mfm.main
pm uninstall -k --user 0 com.nttdocomo.android.devicehelp
pm uninstall -k --user 0 com.felicanetworks.mfm
pm uninstall -k --user 0 com.nttdocomo.android.mascot
pm uninstall -k --user 0 com.nttdocomo.android.databackup
pm uninstall -k --user 0 com.nttdocomo.android.cloudstorageservice
pm uninstall -k --user 0 com.nttdocomo.android.dcmvoicerecognition
pm uninstall -k --user 0 com.nttdocomo.android.photocollection
pm uninstall -k --user 0 com.nttdocomo.android.moneyrecord
pm uninstall -k --user 0 com.facebook.system
pm uninstall -k --user 0 com.sony.tvsideview.videoph
pm uninstall -k --user 0 com.sonyericsson.textinput.chinese
pm uninstall -k --user 0 com.sonyericsson.warrantytime
pm uninstall -k --user 0 com.sonymobile.enterprise.service
pm uninstall -k --user 0 com.sonymobile.gettoknowit
pm uninstall -k --user 0 com.sonymobile.moviecreator
pm uninstall -k --user 0 com.sonymobile.moviecreator.rmm
pm uninstall -k --user 0 com.sonymobile.music.googlelyricsplugin
pm uninstall -k --user 0 com.sonymobile.music.wikipediaplugin
pm uninstall -k --user 0 com.sonymobile.mx.android
pm uninstall -k --user 0 com.sonymobile.sketch
pm uninstall -k --user 0 com.sonymobile.support
pm uninstall -k --user 0 com.facebook.appmanager
pm uninstall -k --user 0 com.facebook.katana
pm uninstall -k --user 0 com.spotify.music
pm uninstall -k --user 0 com.sonymobile.getmore.client
pm uninstall -k --user 0 com.sony.tvsideview.phone
pm uninstall -k --user 0 com.sonyericsson.trackid
pm uninstall -k --user 0 com.amazon.mShop.android.shopping
pm uninstall -k --user 0 com.scee.psxandroid
pm uninstall -k --user 0 com.sonymobile.entrance
pm uninstall -k --user 0 com.s.antivirus
pm uninstall -k --user 0 com.sonyericsson.xhs
pm uninstall -k --user 0 com.sonymobile.xperialounge.services
pm uninstall -k --user 0 com.sonymobile.xperiaservices
pm uninstall -k --user 0 com.sonymobile.music.youtubekaraokeplugin
pm uninstall -k --user 0 com.sonymobile.tvout.wifidisplay
pm uninstall -k --user 0 com.sonymobile.music.youtubeplugin
pm uninstall -k --user 0 com.sonyericsson.trackid.res.overlay_305
{% endhighlight %}

Refrensi tutorial ane: https://webruary.net/mobile/2017-06-09/xperia-z5-compact/
