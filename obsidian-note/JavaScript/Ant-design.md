# Form
1. 可以使用 `shouldUpdate` 来进行条件更新, 例如 `disabled` 选项依赖于其他字段的变化. 
2. `getValueFormEvent` 可以对 `input` 处理. 
```jsx
<Form.Item
    noStyle
    shouldUpdate={(prevValues, currentValues) => true}
>
    {({ getFieldValue }) =>
        getFieldValue('sex') === "women"? (
            <Form.Item
                name="age"
                label="年龄"
                rules={[{ required: true, message: '必填' }]}
            >
                    <Input />
            </Form.Item>
        ) : null
    }
</Form.Item>
```