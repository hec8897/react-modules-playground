# react-module-playground

## Getting Started

```bash
yarn set version berry

yarn dev
```

## react-hook-form

https://react-hook-form.com

### 기본 사용법

```tsx
const {
  register,
  handleSubmit,
  formState: {
    isValid, // values 가 유효할 경우 true
    errors,
  },
} = useForm<Autho>({
  defaultValues: {
    uid: "",
  },
});

const onSubmit = (data: Autho) => {
  postAutho(data);
};

return (
  <form onSubmit={handleSubmit(onSubmit)}>
    <input register={register("uid")} />
  </form>
);
```

### Input 컴포넌트 분리 시

```tsx
const FormInput = forwardRef<HTMLInputElement, IProps>((props, ref) => {
  const { register, type } = props;
  return (
    <InputStyle ref={ref} {...{ ...register, type: type ? type : "text" }} />
  );
});

FormInput.displayName = "FormInput"; // lint 에러 방지
```

## recoil

## react-query

## reChart
