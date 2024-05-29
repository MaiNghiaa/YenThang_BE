
-  CREATE TABLE `user` (
  `UserId` int NOT NULL AUTO_INCREMENT,
  `Username` varchar(255) DEFAULT NULL,
  `Password` varchar(255) DEFAULT NULL,
  `Role` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`UserId`)
) ENGINE=InnoDB AUTO_INCREMENT=9 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci

-  CREATE TABLE `products` (
  `id` int NOT NULL AUTO_INCREMENT,
  `image` varchar(255) DEFAULT NULL,
  `title` varchar(255) DEFAULT NULL,
  `description` text,
  `price` decimal(10,2) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=29 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci

-  CREATE TABLE `Orders` (
  `OrderID` int NOT NULL AUTO_INCREMENT,
  `CustomerName` varchar(255) DEFAULT NULL,
  `TotalPrice` decimal(10,2) DEFAULT NULL,
  `OrderDate` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  `Email` varchar(255) DEFAULT NULL,
  `Phone` varchar(20) DEFAULT NULL,
  `Address` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`OrderID`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci

-  CREATE TABLE `OrderDetails` (
  `OrderDetailID` int NOT NULL AUTO_INCREMENT,
  `OrderID` int DEFAULT NULL,
  `ProductID` int DEFAULT NULL,
  `Quantity` int DEFAULT NULL,
  `UnitPrice` decimal(10,2) DEFAULT NULL,
  PRIMARY KEY (`OrderDetailID`),
  KEY `OrderID` (`OrderID`),
  KEY `ProductID` (`ProductID`),
  CONSTRAINT `orderdetails_ibfk_1` FOREIGN KEY (`OrderID`) REFERENCES `Orders` (`OrderID`),
  CONSTRAINT `orderdetails_ibfk_2` FOREIGN KEY (`ProductID`) REFERENCES `products` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=9 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci

- Thêm data cho products nè
INSERT INTO products (image, title, description, price) VALUES
("img-1.png", "Types of Coffee", "Looking at its layout. The point of", 19.99),
("img-2.png", "Espresso", "Strong and bold espresso shots.", 25.99),
("img-3.png", "Cappuccino", "Creamy and smooth cappuccino.", 22.99),
("img-4.png", "Latte", "Milky and mild latte coffee.", 21.99),
("img-5.png", "Mocha", "Rich and indulgent chocolate mocha.", 24.99),
("img-6.png", "Macchiato", "Espresso with a dash of steamed milk.", 23.99),
("img-7.png", "Americano", "Black coffee with hot water.", 20.99),
("img-8.png", "Iced Coffee", "Chilled and refreshing iced coffee.", 26.99),
("img-9.png", "Affogato", "Espresso poured over vanilla ice cream.", 27.99),
("img-10.png", "Flat White", "Velvety microfoam atop a double shot of espresso.", 23.49),
("img-11.png", "Turkish Coffee", "Rich and aromatic Turkish coffee.", 28.99),
("img-12.png", "Frappuccino", "Creamy blended coffee.", 22.49),
("img-13.png", "Irish Coffee", "Coffee with a dash of Irish whiskey and cream.", 29.99),
("img-14.png", "Pour Over", "Freshly brewed coffee made by pouring hot water over ground coffee beans.", 21.49),
("img-15.png", "Vietnamese Coffee", "Sweetened condensed milk with strong brewed coffee over ice.", 26.49),
("img-16.png", "Cold Brew", "Coffee brewed with cold water over a longer period.", 25.49),
("img-17.png", "Bulletproof Coffee", "Coffee blended with grass-fed butter and MCT oil.", 30.99),
("img-18.png", "Nitro Coffee", "Cold brew coffee infused with nitrogen gas.", 28.49),
("img-19.png", "Turmeric Latte", "Latte made with turmeric and spices.", 23.99),
("img-20.png", "Matcha Latte", "Latte made with finely ground green tea powder.", 24.99);
  -----
- Data cho phần user
- INSERT INTO user (Username, Password, Role) VALUES ('admin', 'admin', 'admin'),
('test1', 'test1', 'user'),('test2', 'test2', 'user'),
