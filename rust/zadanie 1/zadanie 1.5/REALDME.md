## Удалить дубликаты из отсортированного массива
## Задание
Дан целочисленный массив, numsотсортированный в неубывающем порядке , удалить дубликаты на месте так, чтобы каждый уникальный элемент появлялся только один раз . Относительный порядок элементов должен оставаться прежним . Затем вернуть количество уникальных элементов вnums .

Примите во внимание количество уникальных элементов , numsчтобы kбыть принятым, вам необходимо сделать следующее:

Измените массив numsтак, чтобы первые kэлементы numsсодержали уникальные элементы в том порядке, в котором они присутствовали numsизначально. Остальные элементы numsне важны, как и размер nums.
Возвращаться k.
Судья по индивидуальному заказу:
Судья проверит ваше решение с помощью следующего кода:
int[] nums = [...]; // Входной массив
int[] expectedNums = [...]; // Ожидаемый ответ с правильной длиной

int k = removeDuplicates(nums); // Вызывает вашу реализацию
утверждать k == expectedNums.length;
для (int i = 0; i < k; i++) {
    утверждать nums[i] == expectedNums[i];
}
Если все утверждения пройдены, то ваше решение будет принято .

## Код 
``` rust
impl Solution { 
    pub fn remove_duplicates(nums: &mut Vec<i32>) -> i32 { 
        if nums.is_empty() { 
            return 0; 
        } 

        let mut k = 1; 

        for i in 1..nums.len() { 
            if nums[i] != nums[k - 1] { 
                nums[k] = nums[i]; 
                k += 1; 
            } 
        } 

        nums.truncate(k);
        
        k as i32 
    } 
}
```