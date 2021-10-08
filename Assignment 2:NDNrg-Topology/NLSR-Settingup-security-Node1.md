Source : https://named-data.net/doc/NLSR/current/beginners-guide.html

To test the NLSR, the first step is

1. Configure keys and certificates that enforce secure communication between routers.
2. Verify that the computers on the test network are connected, that NFD is running and that the face between computers is configured.
3. Finally, the NLSR configuration file must be edited before running NLSR. The following subsections are provided as a guide for defining and configuring a simple computer network between two computers: router1 and router2.

Setting up the security
Configuring security in an NDN network requires to generate, exchange and install, keys and certificates between the root, site, operator and router computers that form the network [NLSRsecconf], [NLSRdevguide], although in practice, it is possible to keep more than one of these entities in a single machine. The following example and Figure 1 show how to configure security for a single router, called Router X. In this example, the root, site, operator and Router X are in different computers:

![alt img](https://named-data.net/doc/NLSR/current/_images/security_comp.png)


1. At the root server, generate the root key:

<pre>
$ ndnsec-key-gen /ndn/ > root.key
</pre>

2. Generate the certificate for the root key at the root server:
<pre>
$ ndnsec-cert-dump -i /ndn/ > root.cert
</pre>

3. Install the root certificate at the root server:
<pre>
$ ndnsec-cert-install -f root.cert
<pre>

![alt img](https://github.com/syaifulahdan/Mini-NDN-Work/blob/main/Assignment%202:NDNrg-Topology/NDNrg-Image-Node1/NLSR-Image-Node1/nslr-install-rootcert-node1.png.png)
<pre>
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-key-gen /ndn/ > root.key
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-dump -i /ndn/ > root.cert
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR# ndnsec-cert-install -f root.cert
OK: certificate with name [/ndn/KEY/%16%D0%E4%8E%950R4/self/v=1633687187749] has been successfully installed
root@NDN-Node1-ITB:/home/bertopeng17-1/NLSR#
</pre>