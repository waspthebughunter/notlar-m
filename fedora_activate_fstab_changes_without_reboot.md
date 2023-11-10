fedora sistemde fstab dosyasında yapılan değişikliği reboot atmadan aktif hale getirmek


1-) değişikliğe uğrayan kısmı unmount etmek
```
sudo umount /değişen/bağlama/noktası
```
2-) aynı kısmı geri bağlamak
```
sudo mount -a
```
3-) fstab üzerindeki değişikliği aktif etmek
```
sudo systemctl daemon-reload
```
