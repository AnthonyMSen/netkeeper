[Outline]
ÿ������ǰ��Ҫʹ��netkeeper�ű���½
netkeeper�����dialnetkeeper�������
dialnetkeeper�������Լ��������ɵ��ļ�


[detail]
1.����ǰ���޸�netkeeper�ļ�����username=��
password=��������Լ����˻����룬�������벻Ҫ���κ��޸ġ�

2.��PPPOE.conf��dialnetkeeper��netkeeper�����ļ��ƶ���/usr/local/binĿ¼(��/usr/bin/):
sudo mv PPPOE.conf dialnetkeeper netkeeper /usr/local/bin

3.�޸��������ӽӿ��ļ�interfaces:
sudo gedit /etc/network/interfaces
Ȼ�󽫴򿪵��ļ��޸�Ϊ��������
auto lo
iface lo inet loopback 
  
iface dsl-provider inet ppp
pre-up /sbin/ifconfig eth0 up # line maintained by pppoeconf
provider dsl-provider
  
auto eth0
iface eth0 inet dhcp

4. Ϊnetkeeper�ű�����Ȩ��:
sudo chmod 777 /usr/local/bin/netkeeper
sudo chmod 777 /usr/local/bin/dialnetkeeper

5.�Ժ󼴿����ն���ʹ��sudo netkeeper���ţ��ǳ�����Ϊsudo poff -a��


[memo]
  
1.���ڱ������Դ�pppoe�����ļ�����Ŀǰֻ�ʺϲ�������Ĭ��Ϊeth0���û����ʺϾ��󲿷�����������а���߲���������eth0��ͬѧ�뽫PPPOE.conf�е���Ӧeth0�滻���������
     
2.������ı���32λ����"�����˴��ҵ�netkeeper"
