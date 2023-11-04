- birden fazla diski birleştirip hepsini tek bir diskmiş gibi kullanmak için logical volume lar kullanılır
- sistemin kurulu olduğu ana diski diğer diskleri kullanarak büyütmek için;
```
- fdisk ile diski "LİNUX LVM" şeklinde biçimlendirmek gerekli
- fiziksel alanı oluşturmak için "pvcreate /dev/<disk_ismi>"
- hali hazırda bulunan volume grub ı genişletmek için "vgextend vg_ismi /dev/disk_ismi"
- genişletmek istediğimiz alandaki lv için "lvextend /dev/vg_ismi/bölüm_ismi /dev/disk_ismi"
```
