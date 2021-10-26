# Pardus üzerinde .VDI dosyasının QCOW2'ye çevrilmesi

## VDI (Virtual desktop infrastructure - Sanal masaüstü altyapısı) 

VDI, merkezi bir sunucu üzerinde çalışan bir sanal makine içinde bir masaüstü işletim sisteminin barındırılması süreci olarak tanımlanır. VDI, bazen sunucu tabanlı bilgi işlem olarak adlandırılan, istemci/sunucu bilgi işlem modelinin bir varyasyonudur. 

## QCOW2

QCOW2, sanal diskler için bir depolama biçimidir. QCOW, QEMU yazma üzerine kopyalama anlamına gelir. QCOW2 formatı, mantıksal ve fiziksel bloklar arasında bir eşleme ekleyerek fiziksel depolama katmanını sanal katmandan ayırır. 

 

## VDI dosyasının Qcow2'ya Çevrilmesi

 Dönüşümde kullanmak için qemu ve kvm paketleri kurulmalıdır.

``` 
sudo apt-get -y install qemu-kvm virtinst bridge-utils
```

Vdi görüntü dosyasını içeren dizine gidilir.

![Ekran Görüntüsü - 2021-10-06 13-25-39](/home/prds3/Resimler/Ekran Görüntüsü - 2021-10-06 13-25-39.png)

Qemu kullanılarak vdi qcow2 formatına dönüştürülür. Temel olarak yapılan işlem, vdi'yi ham disk görüntülerine dönüştürmektir.

```
qemu-img convert -f vdi -O qcow2 oraclelinux01.vdi oraclelinux01.qcow2 
```

![Ekran Görüntüsü - 2021-10-06 14-50-47](/home/prds3/Resimler/Ekran Görüntüsü - 2021-10-06 14-50-47.png)

