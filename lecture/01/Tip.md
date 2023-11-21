## babel 관련

- react 라이브러리 import 스킵

``` yaml
"babel": {
    "presets": [
      [
        "@babel/preset-react",
        {
          "runtime": "automatic"
        }
      ]
    ]
  }
```

## Webpack 관련

- 확장자 자동인식

```yaml
resolve: {
    extensions: [".js", ".jsx"],
  },
```

## Component 구현시

- `...rest` 활용 (children 포함)

```javascript
const Button = ({ styleType, block, ...rest }) => {
  let className = "Button";
  if (styleType) className += ` ${styleType}`;
  if (block) className += ` block`;

  return <button className={className} {...rest} />;
};

export default Button;
```