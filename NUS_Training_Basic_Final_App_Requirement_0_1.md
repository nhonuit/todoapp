# YÊU CẦU CỦA FINAL APP

## Mô tả
Final app cần làm là một simple web app dùng để quản lý các công việc cần làm (todo list). Người dùng có thể tạo ra các danh sách công việc cần làm (list), sau đó người dùng có add các công việc cần làm (item) vào danh sách đã tạo. Người dùng có thể chia sẻ list của mình với người khác.

App được viết bằng ngôn ngữ Ruby và Rails (một Ruby gem). Sau khi hoàn thành app cần deploy được app của mình lên Heroku (một cloud service)

## Các tính năng yêu cầu

### Sign up

Dùng gem devise để làm tính năng đăng ký cho phép người dùng tạo tài khoản để sử dụng app.

Người dùng cần nhập name, email, password và password confirmation để đăng ký. Email trong app là duy nhất, người dùng không được đăng ký với một email đã tồn tại, nếu người dùng điền email đã tồn tại vào form sign up thì sẽ nhận được message báo lỗi.

Sau khi đăng ký thành công, hệ thống cần gởi mail tới email người dùng đã đăng ký (confirmation email) để yêu cầu người dùng xác nhận email. Khi người dùng click vào link trong confirmation email thì tài khoản của họ sẽ được xác nhận. Lúc này người dùng mới có thể dùng tài khoản đã đăng ký để login vào sẽ dụng app được, nếu người dùng chưa xác nhận email thì không login được vào app.

Dùng Twitter Bootstrap để làm giao diện, form đăng ký cần được validate bằng Jquery Validation để chặn người dùng submit form khi chưa điền đầy để thông tin.

Về giao diện thì không có yêu cầu cụ thể nhưng màn hình làm ra cần phải tương đối dễ nhìn, cân đối, gọn gàng và không bị bể trên cả desktop, tablet và smart phone. Ví dụ: https://bootsnipp.com/snippets/featured/google-style-login


### Sign in

Dùng gem devise để làm tính năng đăng nhập.

Người dùng cần nhập email, password đã đăng ký vào form Sign In để đăng nhập vào app. Khi login không thành công thì phải có message thông báo lỗi.

Dùng Twitter Bootstrap để làm giao diện, form sign in cần được validate bằng Jquery Validation để chặn người dùng submit form khi chưa điền đầy để thông tin.

Về giao diện thì không có yêu cầu cụ thể nhưng màn hình làm ra cần phải tương đối dễ nhìn, cân đối, gọn gàng và không bị bể trên cả desktop, tablet và smart phone. Ví dụ: https://bootsnipp.com/snippets/featured/google-style-login


### Forgot password

Dùng gem devise để làm tính năng forgot password: giúp người dùng thay đổi password khi họ quên password cũ.

Người dùng cần nhập email đã đăng ký vào form Forgot Password để nhận được mail hướng dẫn phục hồi password. Khi người dùng điền một email không tồn tại thì phải có message thông báo lỗi. Khi người dùng click vào link trong email forgot password thì họ sẽ được đưa tới một page để điền password mới.

Dùng Twitter Bootstrap để làm giao diện, form forgot password và nhập password mới cần được validate bằng Jquery Validation để chặn người dùng submit form khi chưa điền đầy để thông tin.

Về giao diện thì không có yêu cầu cụ thể nhưng màn hình làm ra cần phải tương đối dễ nhìn, cân đối, gọn gàng và không bị bể trên cả desktop, tablet và smart phone. Ví dụ: https://bootsnipp.com/snippets/featured/google-style-login


### Layout cho các page sau khi user đã đăng nhập.
Sau khi người đã đăng nhập vào app thì tất cả các page họ có thể truy cập vào sẽ có layout trông giống ví dụ này: https://bootsnipp.com/snippets/featured/simple-admin

  - Header bao gồm logo của app nằm bên trái, bên phải có một dropdown có text là "Hi [tên Người dùng đang login]", dropdown gồm có 2 link: một link dẫn đến trang edit profile và một link logout
  - Menu bên trái gồm có các item sau:

    + Dashboard: show ra toàn bộ các item có due date là hôm nay hoặc trong quá khứ và chưa được đánh dấu là finish. Các item có due date trong hôm nay sẽ hiện ở trên, các item có due date trong quá khứ hiện ở dưới. Item đã quá due date thì sẽ có background màu đỏ nhạt, item có due date hôm nay có background màu vàng nhạt. Các items trên trang này có phân trang và có thể filter theo **list**. Các item này hiện theo dạng grid giống Google Keep, các thông tin hiện ra bao gồm title, description, due date, list’s name (thuộc về list tên gì), owner’s name (item này thuộc về ai). Phần title in đậm, hiển thị tối đa 20 từ. Phần description hiển thị tối đa 150 từ. Nếu title và description dài quá số từ trên thì hiển thị link/icon để *show more* hoặc *show less*. Khi hover vào item thì sẽ hiện ra 3 icon: Edit, Delete, Finish. Edit: dẫn đến trang edit item. Delete: xóa item, chú ý khi nhấn icon delete thì phải show message confirm cho user, user có confirm thì mới xóa. Finish: đánh dấu là item đã được complete.
    + Lists: gồm 2 submenu: My Lists và Shared Lists.


### Dashboard
Show ra toàn bộ các item có due date là hôm nay hoặc trong quá khứ và chưa được đánh dấu là finish. Các item có due date trong hôm nay sẽ hiện ở trên, các item có due date trong quá khứ hiện ở dưới. Item đã quá due date thì sẽ có background màu đỏ nhạt, item có due date hôm nay có background màu vàng nhạt.

Các items trên trang này có phân trang và có thể filter theo **list**.

Các item này hiện theo dạng grid giống Google Keep, các thông tin hiện ra bao gồm title, description, due data, list’s name (thuộc về list tên gì), owner’s name (item này thuộc về ai). Phần title in đậm, hiển thị tối đa 20 từ. Phần description hiển thị tối đa 150 từ. Nếu title và description dài quá số từ trên thì hiển thị link/icon để *show more* hoặc *show less*. Khi hover vào item thì sẽ hiện ra 3 icon: Edit, Delete, Finish.

  - Edit: dẫn đến trang **Edit item**. Trang này giống với trang **Create new item** (xem requirement ở các phần sau).
  - Delete: xóa item, chú ý khi nhấn icon delete thì phải show message confirm cho user, user có confirm thì mới xóa. Chỉ có user là người tạo ra item thì mới thấy được icon này và xóa được item. User được share ko thể xóa được item.
  - Finish: đánh dấu là item đã được complete.


### My Lists
Show toàn bộ các list của người dùng đang đăng nhập. Hiển thị theo dạng grid, list mới hơn hiển thị trước, cũ hơn hiển thị sau, thông tin mỗi list bao gồm name, danh sách participations và số item trong list. Có phân trang và có thể search by name. Hover vào sẽ hiện ra 2 icons: Edit, Delete.

  - Edit: dẫn đến trang **Edit list**. User có thể edit name và danh sách participation. Danh sách participation nếu được thì có thể làm kiểu autocomplete, nếu không thì làm dạng multiple checkboxes (hiện ra tất cả user trong hệ thống rồi check chọn).
  - Delete: xóa list, chú ý khi nhấn icon delete thì phải show message confirm cho user, user có confirm thì mới xóa.

Khi click và list sẽ đến trang details của 1 list. Trang details sẽ hiện thị ra tất cả các item thuộc về list đó, trang này giao diện sẽ giống Dashboard.

Phía trên danh sách các lists sẽ có một button **Create new list**, nhấn vào button này sẽ dẫn đến trang tạo list mới, xem requirement ở phần dưới.


### Create new list
Tại trang **Create new list** sẽ có textbox để người dùng điền name và có search box (autocomplete) hoặc  multiple checkboxes để chọn participations giống với trang **Edit list**. **Name** là require, **participations** là optional.

Sau khi người dùng submit tạo một list thành công thì sẽ quay lại màn hình **My Lists** và có message thông báo.


### Shared Lists
Show toàn bộ các list của người dùng khác share cho người dùng đang đăng nhập. Hiển thị theo dạng grid, list mới hơn hiển thị trước, cũ hơn hiển thị sau, thông tin mỗi list bao gồm name và số item trong list. Có phân trang và có thể search by name.

Khi click và list sẽ đến trang details của 1 list. Xem requirement của trang này ở phần kế tiếp.


### View list's details
Trang details sẽ hiện thị ra tất cả các item thuộc về list đó, trang này về giao diện sẽ giống Dashboard. Trang này sẽ phân trang giống Dashboard nhưng không có filter theo **list** giống Dashboard mà sẽ có một select box phía trên các items để người dùng có thể filter theo 3 options:

  - All: show ra toàn bộ các item trong list
  - Finished: show ra bộ các item đã hoàn thành trong list
  - Unfinished: show ra bộ các item chưa hoàn thành trong list

Phía trên danh sách các lists sẽ có một button **Create new item**, nhấn vào button này sẽ dẫn đến trang tạo item mới. Xem requirement cho trang này ở phần sau.


### Create new item
Có textbox để người dùng điền title, description và có date picker để người dùng chọn due date. 3 fields này đều require.

Sau khi người dùng submit tạo một item thành công thì sẽ quay lại màn hình **View list's details** và có message thông báo.


### Authentication & Authorization
App phải đảm bảo được những điều sau đây:

  - Một người dùng chưa đăng nhập vào hệ thống thì không thể sử dụng bất cứ tính năng nào liên quan đến list và item.
  - Một list chỉ được view bởi người tạo ra và những người được share.
  - Một list chỉ có thể được update và delete bởi chính người tạo ra nó.
  - Người dùng có thể tạo ra item mới cho list của chính mình hoặc một list được share cho mình. Không thể tạo item cho một list mà mình không phải là người tạo hoặc là người được share.
  - Người dùng có thể edit và đánh dấu finish một item của mình hoặc được share cho mình. Người dùng không thể delete một item nếu nó không phải thuộc về list của mình.




























