## Повернуть изображение
## Задание
Вам дано n x n2D- matrixпредставление изображения, поверните изображение на 90 градусов (по часовой стрелке).

Вам нужно повернуть изображение на месте , что означает, что вам нужно напрямую изменить входную 2D-матрицу. НЕ выделяйте другую 2D-матрицу и не делайте поворот.
Пример 1:
Вход: матрица = [[1,2,3],[4,5,6],[7,8,9]]
Выход: [[7,4,1],[8,5,2],[9,6,3]]
## Код
``` rust
impl Solution { 
    pub fn rotate(matrix: &mut Vec<Vec<i32>>) { 
        matrix.reverse(); 

        let n = matrix.len();
        for i in 0..n {
            for j in 0..i {
                let temp = matrix[i][j];
                matrix[i][j] = matrix[j][i];
                matrix[j][i] = temp;
            } 
        } 
    } 
}
```
## Скриншот 
![alt text](https://github.com/Vladiiimir8/plyaskin_20421/blob/main/rust/zadanie%201/zadanie%201.6/screen6.png?raw=true)