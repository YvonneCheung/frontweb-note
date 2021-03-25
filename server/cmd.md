- 查看所有的端口号

  ```powershell
  netstat -ano :
  ```

- 具体查看端口的号

  ```powershell
  netstat -ano |findstr “端口号”
  ```

- 通过pid来获取进程的信息

  ```po
  tasklist |findstr pid
  ```

- 杀死端口进程：

  ```powershell
  taskkill -pid 端口号 -f
  ```

  

