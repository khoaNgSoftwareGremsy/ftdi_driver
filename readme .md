#Driver for FT4232 

##Introduction 
 - Có 2 loại driver cho các loại USB-TTL của dòng FTDI là VCP và D2XX Drivers. D2XX được dùng để truy cập vào firmware của FT4232 nên hiện tại sẽ không sử dụng driver này. VCP được dùng cho máy tính nhận biết các loại USB FT là một hay nhiều cổng COM ảo để có thể thực hiện giao tiếp serial.
 
##How to install driver VCP to S5L
  - NOTE: Vì S5L hiện tại đang build bằng linux kernel 4.9.224 nên lưu ý tải driver VCP phù hợp nếu có thay đổi phiên bản trong tương lai. Reference Link: https://elixir.bootlin.com/linux/v4.9.224/source/drivers/usb/serial/ftdi_sio_ids.h 
  - STEP 1: git clone repository này vào tsdk-kernel-module của oclea-sdk
  - STEP 2: Vô file CMakeLists.txt -> trong mục set( KERNEL_MODULE_LIST) add thêm tên file ftdi_sio
  - STEP 3: Ra ngoài Oclea-sdk để tiến hành build chương trình.
  	sudo ./build_app.sh -p s5l
  Sau khi build thành công tiến hành tạo ảnh và nạp ảnh.
  Test cắm FT4232 vào cổng USB của S5L và kiếm tra S5L có phát hiện được các cổng của FT4232 hay không.
  
  
  
  