##Android 4.4或以上##
**Dat轉Img(Ext4)**


./sdat2img.py system.transfer.list system.new.dat system.img


**掛載System**


./mount -t ext4 -o loop system.img system


**將掛載的System寫成Img(普通)**


./make_ext4fs -T 0 -S file_contexts -l 1306001408B -a system system_new.img system

(1306001408B爲system.img大小)


**將Img(Ext4)轉成Dat**


./rimg2sdat system_new.img


##Android 4.3或以下##
**掛載System**


./mount -t ext4 -o loop system.img system


**將掛載的System寫成Img(普通)**


./make_ext4fs -l 1306001408B -s -a system system_new.img system

(1306001408B爲system.img大小)


**將Img(普通)轉成Img(Ext4)**


./simg2img system_new.img system_ext4.img


**將Img(Ext4)轉成Dat**


./rimg2sdat system_ext4.img


##需要使用的程式##

**sdat2img.py**

**make_ext4fs**

**simg2img**

**rimg2sdat**

##其他指令##
resize2fs system.img 318848
