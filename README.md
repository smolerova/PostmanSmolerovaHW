# PostmanSmolerovaHW

http://162.55.220.72:5005/first
1. Отправить запрос.
2. Статус код 200
 ```
 pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```
3. Проверить, что в body приходит правильный string.
```
pm.test("Проверить, что в body приходит правильный string.", function () {
    pm.expect(pm.response.text()).to.equals("This is the first responce from server!");
});
```

http://162.55.220.72:5005/user_info_3
1. Отправить запрос.
2. Статус код 200
```
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var jsonData = pm.response.json();
console.log(jsonData);
```
4. Проверить, что name в ответе равно name s request (name вбить руками.)
```
pm.test("Проверить, что name в ответе равно name в request", function () {
    pm.expect(jsonData.name).to.eql("Nata");
});
```
5. Проверить, что age в ответе равно age s request (age вбить руками.)
```
pm.test("Проверить, что age в ответе равно age в request ", function () {
    pm.expect(jsonData.age).to.eql("30");
});
```
6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```
pm.test("Проверить, что salary в ответе равно salary в request", function () {
    pm.expect(jsonData.salary).to.eql(500);
});
```
7. Спарсить request.
```
var reqData = request.data;
```
8. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Проверить, что name в ответе равно name в request (name забрать из request.)", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```
9. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Проверить, что age в ответе равно age в request (age забрать из request.)", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
});
```
10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Проверить, что salary в ответе равно salary в request (salary забрать из request.)", function () {
    pm.expect(jsonData.salary).to.eql(+reqData.salary);
});
```

11. Вывести в консоль параметр family из response.
```
console.log(jsonData.family);
```
12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```
pm.test("Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)", function () {
    pm.expect(jsonData.family.u_salary_1_5_year).to.eql(+request.data.salary*4);
});
```

http://162.55.220.72:5005/object_info_3
1. Отправить запрос.
2. Статус код 200
```
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var jsonData = pm.response.json();
console.log(jsonData);
```
4. Спарсить request.
```
var reqData = pm.request.url.query.toObject();
console.log(reqData);
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Проверить, что name в ответе равно name в request (name забрать из request.)", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
    });
```
6. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Проверить, что age в ответе равно age в request (age забрать из request.)", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
    });
```
7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Проверить, что salary в ответе равно salary в request (salary забрать из request.)", function () {
    pm.expect(jsonData.salary).to.eql(+reqData.salary);
    });
 ```
8. Вывести в консоль параметр family из response.
```
console.log(jsonData.family);
```
9. Проверить, что у параметра dog есть параметры name.
```
pm.test("Проверить, что у параметра dog есть параметры name", function () {
    pm.expect(jsonData.family.pets.dog).to.have.property('name');
    });
```
10. Проверить, что у параметра dog есть параметры age.
```
pm.test("Проверить, что у параметра dog есть параметры age", function () {
    pm.expect(jsonData.family.pets.dog).to.have.property('age');
    });
```
11. Проверить, что параметр name имеет значение Luky.
```
pm.test("Проверить, что параметр name имеет значение Luky", function () {
    pm.expect(jsonData.family.pets.dog.name).to.eql('Luky');
    });
```
12. Проверить, что параметр age имеет значение 4.
```
pm.test("Проверить, что параметр age имеет значение 4", function () {
    pm.expect(jsonData.family.pets.dog.age).to.eql(+'4');
    });
```

http://162.55.220.72:5005/object_info_4
1. Отправить запрос.
2. Статус код 200
```
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var jsonData = pm.response.json();
console.log(jsonData);
```
4. Спарсить request.
```
var reqData = pm.request.url.query.toObject();
console.log(reqData);
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Проверить, что name в ответе равно name в  request (name забрать из request)", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
    });
```
6. Проверить, что age в ответе равно age из request (age забрать из request.)
```
pm.test("Проверить, что age в ответе равно age из request (age забрать из request.)", function () {
    pm.expect(jsonData.age).to.eql(+reqData.age);
    });
```
7. Вывести в консоль параметр salary из request.
```
console.log(reqData.salary);
```
8. Вывести в консоль параметр salary из response.
```
console.log(jsonData.salary);
```
9. Вывести в консоль 0-й элемент параметра salary из response.
```
console.log(jsonData.salary[0]);
```
10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```
console.log(jsonData.salary[1]);
```
11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```
console.log(jsonData.salary[2]);
```
12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```
pm.test("Проверить, что 0-й элемент параметра salary равен salary в request (salary забрать из request.)", function () {
    pm.expect(jsonData.salary[0]).to.eql(+reqData.salary);
    });
```
13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```
pm.test("Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)", function () {
    pm.expect(jsonData.salary[1]).to.eql(+reqData.salary*2);
    });
```
14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```
pm.test("Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)", function () {
    pm.expect(jsonData.salary[2]).to.eql(+reqData.salary*3);
    });
```
15. Создать в окружении переменную name
```
pm.environment.set("name","Kate");
```  
16. Создать в окружении переменную age
```
 pm.environment.set("age","50");
```
17. Создать в окружении переменную salary
```
pm.environment.set("salary","1500");
```
18. Передать в окружение переменную name
19. Передать в окружение переменную age
20. Передать в окружение переменную salary
21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```
console.log (" Написать цикл который выведет в консоль по порядку элементы списка из параметра salary:");

    jsonData.salary.forEach(function(s) {
        console.log(s);
    }); 
```
```
 jsonData.salary.forEach(s => console.log(s));
```


http://162.55.220.72:5005/user_info_2
1. Вставить параметр salary из окружения в request
2. Вставить параметр age из окружения в age
3. Вставить параметр name из окружения в name
4. Отправить запрос.
5. Статус код 200
6. Спарсить response body в json.
7. Спарсить request.
8. Проверить, что json response имеет параметр start_qa_salary
9. Проверить, что json response имеет параметр qa_salary_after_6_months
10. Проверить, что json response имеет параметр qa_salary_after_12_months
11. Проверить, что json response имеет параметр qa_salary_after_1.5_year
12. Проверить, что json response имеет параметр qa_salary_after_3.5_years
13. Проверить, что json response имеет параметр person
14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
20. Проверить, что что параметр u_age равен age из request (age забрать из request.)
21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
