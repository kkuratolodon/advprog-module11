# Reflection Module 11

## Reflection on Hello Minikube
1. Compare the application logs before and after you exposed it as a Service. Try to open the app several times while the proxy into the Service is running. What do you see in the logs? Does the number of logs increase each time you open the app

    Before:
    ![alt text](image.png)

    After:
    ![alt text](image-1.png)

    Sebelum aplikasi dibuat sebagai service, log hanya menunjukkan informasi bahwa server telah dimulai pada port tertentu. Namun, setelah aplikasi diekspos sebagai service, log menunjukkan adanya aktivitas permintaan HTTP GET. Ini terlihat dari perbedaan isi log, di mana sebelum diekspos hanya mencatat informasi server, sementara setelah diekspos mencatat riwayat permintaan HTTP GET yang meningkat setiap kali halaman web aplikasi disegarkan.

2. Notice that there are two versions of `kubectl get` invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to
`kube-system`.

    Opsi -n pada perintah kubectl digunakan untuk menentukan namespace tertentu dalam cluster Kubernetes. Namespace berfungsi untuk memisahkan dan mengorganisir sumber daya dalam kluster. Jika menggunakan opsi -n kube-system, perintah kubectl get hanya akan menampilkan objek yang berada di dalam namespace kube-system. Tanpa opsi -n, kubectl secara default akan mencari objek dalam namespace default. Oleh karena itu, jika output tidak menampilkan pods atau services, kemungkinan besar sumber daya tersebut berada di namespace lain yang tidak ditentukan dalam perintah tersebut.