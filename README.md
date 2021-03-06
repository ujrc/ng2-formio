Form.io Angular 2 Renderer
---------------------------
This library serves as a Dynamic JSON Powered Form rendering library for [Angular 2](https://angular.io). This works by
providing a JSON schema to a ```<formio>``` Angular 2 component, where that form is dynamically rendered within the front
end application. This allows forms to be dynamically built using JSON schemas.

Example
---------------------------
You can easily render a form within your Angular 2 application by referencing the URL of that form as follows.

```
<formio src='https://examples.form.io/example'></formio>
```

You can also pass the JSON form directly to the renderer as follows.

```
<formio [form]="{
    title: 'My Test Form',
    components: [
        {
            "type": "textfield",
            "input": true,
            "tableView": true,
            "inputType": "text",
            "inputMask": "",
            "label": "First Name",
            "key": "firstName",
            "placeholder": "Enter your first name",
            "prefix": "",
            "suffix": "",
            "multiple": false,
            "defaultValue": "",
            "protected": false,
            "unique": false,
            "persistent": true,
            "validate": {
                "required": true,
                "minLength": 2,
                "maxLength": 10,
                "pattern": "",
                "custom": "",
                "customPrivate": false
            },
            "conditional": {
                "show": "",
                "when": null,
                "eq": ""
            }
        },
        {
            "type": "textfield",
            "input": true,
            "tableView": true,
            "inputType": "text",
            "inputMask": "",
            "label": "Last Name",
            "key": "lastName",
            "placeholder": "Enter your last name",
            "prefix": "",
            "suffix": "",
            "multiple": false,
            "defaultValue": "",
            "protected": false,
            "unique": false,
            "persistent": true,
            "validate": {
                "required": true,
                "minLength": 2,
                "maxLength": 10,
                "pattern": "",
                "custom": "",
                "customPrivate": false
            },
            "conditional": {
                "show": "",
                "when": null,
                "eq": ""
            }
        },
        {
            "input": true,
            "label": "Submit",
            "tableView": false,
            "key": "submit",
            "size": "md",
            "leftIcon": "",
            "rightIcon": "",
            "block": false,
            "action": "submit",
            "disableOnInvalid": true,
            "theme": "primary",
            "type": "button"
        }
    ]
}"></formio>
```

This is a very simple example. This library is capable of building very complex forms which include e-signatures, columns,
panels, field conditionals, validation requirements, and the list goes on and on.

Usage
----------------
To use this library within your project, you will first need to install it as a dependency.

```
npm install --save ng2-formio
```

You can now include the module in your Angular 2.0 application like so.

```
import { FormioModule } from 'ng2-formio';
@NgModule({
    imports: [ BrowserModule, ReactiveFormsModule, FormioModule ],
    declarations: [ AppComponent ],
    bootstrap: [ AppComponent ]
})
export class AppModule { }
```

Events
------------
With the ```<formio>``` directive, you can register for a number of different events that fire as the Form is being used and submitted. These events can be attached with the typical Angular 2 way using the following syntax.

```
<formio src="https://examples.form.io/example" (submit)="onSubmit($event)"></formio>
```

The following events are provided.

<table>
    <thead>
        <tr>
        <th>Name</th>
        <th>Description</th>
        </tr>
    </thead>
    <tr>
        <th>(submit)</th>
        <td>Called when the form is submitted. The submission object is passed to the callback function.</td>
    </tr>
    <tr>
        <th>(render)</th>
        <td>Called when the form is done rendering.</td>
    </tr>
    <tr>
        <th>(beforeSubmit)</th>
        <td>Called before a submission is made where it is triggered synchronously. The submission object is passed to the callback function.</td>
    </tr>
    <tr>
        <th>(change)</th>
        <td>Called when the form has been changed as in when someone is filling it out.</td>
    </tr>
    <tr>
        <th>(invalid)</th>
        <td>Called when the form is invalid.</td>
    </tr>
</table>

For an example of an application using Form.io, you can look at the [Examples Folder](https://github.com/formio/ng2-formio/tree/master/example)

Try it out
-----------------
To see this working within a live application, you can clone our fork of the amazing [ng2-admin](https://github.com/formio/ng2-admin) theme. Then do the following.

```
npm install
npm start
```

You can now see the Form.io section within the **Forms | Dynamic Forms** section. 

For a visual of the changes that needed to happen to incorporate Form.io into this theme, then [take a look at the following diff](https://github.com/formio/ng2-admin/compare/20031c3980a57291c211dee669b36e933adb751e...master)


Using with Form.io
-----------------
<a href="https://form.io" target="_blank">Form.io</a> is a combined form and data management API platform created for developers who are building "Serverless" form-based applications.  Form.io provides an easy drag-and-drop form builder workflow allowing you to build complex forms for enterprise applications quickly and easily. These forms are then embedded directly into your application with a single line of code that dynamically renders the form (using Angular or React) in your app while at the very same time generating the RESTful API to support those forms. The Form.io platform also offers numerous 3rd-party services that are fully integrated into the form building process allowing you to extend the power and capability of your apps while saving time and effort.

You can use this renderer with Form.io by simply pointing the ```src``` parameter to the URL of the form. For example, the following URL points to the JSON schema of a form built on Form.io.

  https://pjmfogrfqptslvi.form.io/test
  
To render this form, you simply provide that URL to the ```<formio>``` directive like so.

```<formio src="https://pjmfogrfqptslvi.form.io/test"></formio>```

Not only will this render the form, but it will also submit that form to the provided API endpoint.

