# Shape
Bước 1: Định nghĩa lớp Shape
Tạo file với tên Shape.php, bên trong chúng ta sẽ viết code để định nghĩa lớp hình học.

Mã PHP:

class Shape{
    public $name;

    public function __construct($name)
    {
        $this->name = $name;
    }

    public function show(){
        return "I am a shape. My name is $this->name";
    }
}
Bước 2: Định nghĩa lớp Circle, kế thừa từ lớp Shape

Tạo file với tên Cricle.php, bên trong chúng ta sẽ viết code định nghĩa lớp hình tròn được kế thừa các thuộc tính và phương thức từ lớp hình học.

Mã PHP:

include_once ('Shape.php');
class Circle extends Shape {
 public $radius;

 public function __construct($name, $radius)
 {
     parent::__construct($name);
     $this->radius = $radius;
 }

 public function calculateArea(){
     return pi() * pow($this->radius, 2);
 }

 public function calculatePerimeter(){
     return pi() * $this->radius * 2;
 }
}
Bước 3: Định nghĩa lớp Cylinder, kế thừa từ lớp Circle

Tạo file với tên Cylinder, bên trong chúng ta sẽ viết code để định nghĩa lớp hình trụ bao gồm các thuộc tính, phương thức riêng đặc trưng và kế thừa các thuộc tính và phương thức từ lớp hình tròn.

Mã PHP:

include_once ('Circle.php');
class Cylinder extends Circle {
 public $height;

 public function __construct($name, $radius, $height)
 {
     parent::__construct($name, $radius);
     $this->height = $height;
 }

 public function calculateArea()
 {
     return parent::calculateArea() * 2 + parent::calculatePerimeter() * $this->height;
 }

 public function calculateVolume(){
     return parent::calculateArea() * $this->height;
 }
}
Bước 4: Định nghĩa lớp Rectangle, kết thừa từ lớp Shape

Tạo file với tên Rectangle.php, bên trong chúng ta sẽ viết code định nghĩa lớp hình tròn được kế thừa các thuộc tính và phương thức từ lớp hình học.

Mã PHP:

include_once ('Shape.php');
class Rectangle extends Shape{
 public $width;
 public $height;

 public function __construct($name, $width, $height)
 {
     parent::__construct($name);
     $this->width = $width;
     $this->height = $height;
 }

 public function calculateArea(){
      return $this->height * $this->width;
 }

 public function calculatePerimeter(){
      return ($this->height + $this->width) * 2;
 }
}
Bước 5: Định nghĩa lớp Square, kết thừa từ lớp Rectangle

Tạo file với tên Square.php, bên trong chúng ta sẽ viết code định nghĩa lớp hình tròn được kế thừa các thuộc tính và phương thức từ lớp hình chữ nhật.

Mã PHP:

include_once ('Rectangle.php');
class Square extends Rectangle{
 public function __construct($name, $width)
 {
 parent::__construct($name, $width, $width, $width);
 }
}
Bước 6: Tạo các đối tượng, gọi các phương thức và quan sát kết quả

Tạo một hình tròn, tính diện tích và chu vi của hình tròn đó

Tạo một hình trụ, tính diện tích, chu vi và thể tích của hình trụ đó

Tạo một hình chữ nhật, tính diện tích và chu vi của hình chữ nhật đó

Tạo một hìnhh vuông, tính diện tích và chu vi của hình vuông đó

include_once ('Circle.php');
include_once ('Cylinder.php');
include_once ('Rectangle.php');
include_once ('Square.php');

$circle = new Circle('Circle 01', 3);
echo 'Circle area: ' . $circle->calculateArea() . '<br />';
echo 'Circle perimeter: ' . $circle->calculatePerimeter() . '<br />';

$cylinder = new Cylinder('Cylinder 01', 3 , 4);
echo 'Cylinder area: ' . $cylinder->calculateArea() . '<br />';
echo 'Cylinder perimeter: ' . $cylinder->calculatePerimeter() . '<br />';

$rectangle = new Rectangle('Rectangle 01', 3 , 4);
echo 'Rectangle area: ' . $rectangle->calculateArea() . '<br />';
echo 'Rectangle perimeter: ' . $rectangle->calculatePerimeter() . '<br />';

$square = new Square('Square 01', 4 , 4, 4);
echo 'Rectangle area: ' . $square->calculateArea() . '<br />';
echo 'Rectangle perimeter: ' . $square->calculatePerimeter() . '<br />';
