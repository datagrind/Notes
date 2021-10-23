# HTML Tables and Forms

## Tables

Tables are used to arrange content into rows and columns in a tabular format.  

This:

```html
<table>
    <thead>
        <tr>
            <th>Numbers</th>
            <th>Letters</th>
        </tr>
    </thead>
        <tr>              // The first table row
            <td>1</td>    // The table data element, which holds individual cells
            <td>A</td>
        </tr>             // Closing the row
        <tr>              // Second row
            <td>2</td>    // The table data elements for the second row
            <td>B</td>
        </tr>             // Closing the row
        <tr>              // Third Row
            <td>3</td>    // The table data elements for the third row
            <td>C</td>
        </tr>             // Closing the row
    </table>              // Closing the table
```

    Makes This:
<table>
    <thead>
        <tr>
            <th>Numbers</th>
               <th>Letters</th>
        </tr>
    </thead>
        <tr>              
            <td>1</td>  
            <td>A</td>
        </tr>             
        <tr>              
            <td>2</td>    
            <td>B</td>
        </tr>
        <tr>
            <td>3</td>    
            <td>C</td>
        </tr>           
    </table>              




