# AdvProg Module 10

## Reflection on Hello Minikube

> Compare the application logs before and after you exposed it as a Service. Try to open the app several times while the proxy into the Service is running. What do you see in the logs? Does the number of logs increase each time you open the app?

![Before exposing as service](./before_expose.png)
Gambar di atas merupakan kondisi logs sebelum saya mengexpose aplikasi sebagai suatu Service. Seberapa banyak saya mencoba mengakses aplikasi di port 8080, tidak pernah berhasil dan logs tetap hanya menampilkan hal yang sama.

![After exposing as service 1](./after_expose_1.png)
Gambar di atas merupakan kondisi logs setelah saya mengexpose aplikasi sebagai suatu Service. Dapat dilihat bahwa terdapat 2 baris logs baru, yaitu logs GET /, yang menandakan saya berhasil mengunjungi aplikasi tersebut dengan GET request.

![After exposing as service 2](./after_expose.png)
Gambar di atas adalah kondisi logs setelah saya mengunjungi aplikasinya kembali. Dapat dilihat bahwa logs bertambah lagi sebanyak 2 baris yang isinya sama seperti logs sebelumnya, hanya berbeda waktunya. 

> Notice that there are two versions of `kubectl get` invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to `kube-system`. What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?

Opsi `-n` pada `kubectl get` adalah opsi yang menspesifikasikan dari `namespace` mana `kubectl` harus mengambil objek yang diminta pengguna (seperti `pods` atau `service`). `namespace` disini dapat digambarkan seperti suatu folder, sehingga dengan menspesifikasikan `namespace` dengan opsi `-n`, kita memberi tahu `kubectl` dari folder mana mereka harus mengambil objek yang diminta. Secara *default*, jika tidak diberikan opsi `-n`, `namespace` yang digunakan adalah `default`.
