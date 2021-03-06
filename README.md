﻿# react-native-tableview

The TableView component is for outputting data in table format. The following constitute the props for the TableView Component:

1.  <b>title</b> - title for the table, default is Data Table,
2.  <b>titleColor</b> - color of title text, default is dodgerblue,
3.  <b>defaultColor</b>- the default color for general use in the table eg in horizontal lines. Default is dodgerblue,
4.  <b>data</b> - the data to show in the table eg,<code>
    [
    {
    firstName: "Test 1 Firstname",
    lastName: "Test 1 Lastname",
    age: 5,
    },
    {
    firstName: "Test 2 Firstname",
    lastName: "Test 2 Lastname",
    age: 30,
    },
    {
    firstName: "Test 3 Firstname",
    lastName: "Test 3 Lastname",
    age: 45,
    }...]
    </code><br/>

5.  <b>headers</b> - the array of header objects with field names as in data in the form: <code>
    [{ field: "firstName", title: "First Name", size: "34%" },
    { field: "lastName", title: "Last Name", size: "33%" },
    { field: "age", title: "Age", size: "33%" }]
    </code><br/>

- the size is the width of the column relative to other columns(expressed as a %)
- title becomes the column header
- field is the key to extract data, example: celldata=data[field]

6.  <b>paginate</b> - flag to determine whether to show pagination controls, defaults to true,
7.  <b>setItemsPerPage</b> - the function to set itemPerPage value (implement using useState hook),,
8.  <b>setPage</b> - the function to set page value (implement using useState hook),
9.  <b>page</b> - the initial page to render, default is 0.
10. itemsPerPage - initial number of items per page. Preferably on of the elements of <b>pageOptions</b>,
11. <b>pageOptions</b> - the array of number of Items per page options eg [5,10,20],
12. <b>headerColor</b> - color of the headers, default is dodgerblue.
13. <b>firstColumnColor</b> - color to apply to first column text, default is dodgerblue.
14. <b>footerColor</b> - color to apply to footer component text, default is "dodgerblue".
15. <b>highlightRows</b> - prop to highlight rows and make stripped table, default is true.
16. <b>highlightColumns</b> - prop to highlight column backgrounds, only visible in the header, default is false
17. <b>padding</b> - the horizontal padding that separates cells ie. separates columns
18. <b>alignColumns</b> - alignment style for all other columns except first column, defaiult is "center".
19. <b>alignFirstColumn</b> -alignment style for first column contents, default is "flex-start".

<b>EXAMPLE</b>
<code>

  <pre>
import { StyleSheet, Text, View } from "react-native";
import React, { useState } from "react";
import TableView from "./TableView";

export default function Example() {
  const optionsPerPage = [3, 5, 10, 15, 50];
  const [itemsPerPage, setItemsPerPage] = useState(optionsPerPage[1]);
  const [page, setPage] = useState(0);

  const headers = [
    { field: "firstName", title: "First Name", size: "34%" },
    { field: "lastName", title: "Last Name", size: "33%" },
    { field: "age", title: "Age", size: "33%" },
  ];

  const data = [
    {
      firstName: "Test 1 Firstname",
      lastName: "Test 1 Lastname",
      age: 5,
    },
    {
      firstName: "Test 2 Firstname",
      lastName: "Test 2 Lastname",
      age: 30,
    },
    {
      firstName: "Test 3 Firstname",
      lastName: "Test 3 Lastname",
      age: 45,
    },
    {
      firstName: "Test 4 Firstname",
      lastName: "Test 4 Lastname",
      age: "19",
    },
    {
      firstName: "Test 6 Firstname",
      lastName: "Test 6 Lastname",
      age: 5,
    },
    {
      firstName: "Test 7 Firstname",
      lastName: "Test 7 Lastname",
      age: 23,
    },
    {
      firstName: "Test 8 Firstname",
      lastName: "Test 8 Lastname",
      age: 25,
    },
    {
      firstName: "Test 9 Firstname",
      lastName: "Test 9 Lastname",
      age: "85",
    },
    {
      firstName: "Test 10 Firstname",
      lastName: "Test 10 Lastname",
      age: 59,
    },
    {
      firstName: "Test 11 Firstname",
      lastName: "Test 11 Lastname",
      age: 30,
    },
    {
      firstName: "Test 12 Firstname",
      lastName: "Test 12 Lastname",
      age: 10,
    },
    {
      firstName: "Test 13 Firstname",
      lastName: "Test 13 Lastname",
      age: 41,
    },
    {
      firstName: "Test 14 Firstname",
      lastName: "Test `4 Lastname",
      age: "55",
    },
    {
      firstName: "Test 15 Firstname",
      lastName: "Test 15 Lastname",
      age: 15,
    },
    {
      firstName: "Test 16 Firstname",
      lastName: "Test 16 Lastname",
      age: 20,
    },
    {
      firstName: "Test 17 Firstname",
      lastName: "Test 17 Lastname",
      age: 25,
    },
    {
      firstName: "Test 18 Firstname",
      lastName: "Test 18 Lastname",
      age: "55",
    },
  ];

 </pre>
  </code>
 
 
 The return method should now have the TableView and the intended props as shown below:
 <code>
  <pre>
  return (
    <View style={{ width: "100%", height: "100%" }}>
      &ltTableView
        title={"Example Table"}
        headers={headers}
        data={data}
        pageOptions={optionsPerPage}
        itemsPerPage={itemsPerPage}
        setItemsPerPage={setItemsPerPage}
        page={page}
        setPage={setPage}
        highlightRows={true}
        highlightColumns={false}
        paginate={true}
        headerColor={"dodgerblue"}
        firstColumnColor={"dodgerblue"}
        padding={true}
        footerColor={"darkgreen"}
      /&gt
    </View>
    )
    </pre>
  </code>
