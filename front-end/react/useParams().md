# useParams()

- **React Router**에서 제공하는 훅으로, URL에 포함된 동적 파라미터 값을 가져오는 데 사용됩니다. 주로 경로에 동적으로 변하는 값이 있을 때, 해당 값을 컴포넌트에서 쉽게 사용할 수 있도록 해줍니다.
- 경로가 `/product/:id`일 때 `id`는 동적 파라미터이며, URL 경로에서 동적 파라미터를 가져와 객체로 반환합니다. 예를 들어, URL에 상품 ID, 사용자 ID와 같은 값이 있을 때 이를 추출하는 데 사용됩니다.

```javascript
import { BrowserRouter, Route, Routes } from 'react-router-dom';
import ProductDetail from './ProductDetail';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/products/:id" element={<ProductDetail />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```
```javascript
import { useParams } from 'react-router-dom';
import { useEffect, useState } from 'react';

const products = [
  { id: '1', name: 'Tent', price: 100 },
  { id: '2', name: 'Sleeping Bag', price: 50 },
  { id: '3', name: 'Camping Chair', price: 30 },
];

const ProductDetail = () => {
  const { id } = useParams(); // URL의 id 값 추출
  const [product, setProduct] = useState(null);

  useEffect(() => {
    // URL의 id 값과 일치하는 제품 찾기
    const foundProduct = products.find((product) => product.id === id);
    setProduct(foundProduct);
  }, [id]);

  if (!product) {
    return <div>Product not found</div>;
  }

  return (
    <div>
      <h1>{product.name}</h1>
      <p>Price: ${product.price}</p>
    </div>
  );
};

export default ProductDetail;
