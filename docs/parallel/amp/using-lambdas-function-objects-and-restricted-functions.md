---
title: "ラムダ、関数オブジェクト、および制限関数の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
caps.latest.revision: 10
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ラムダ、関数オブジェクト、および制限関数の使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アクセラレータで実行する C\+\+ AMP コードは [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) メソッドへの呼び出しで引数として指定されます。  その引数としてラムダ式または関数オブジェクト \(ファンクター\) を指定できます。  また、ラムダ式や関数オブジェクトでは、C\+\+ AMP 制限関数を呼び出すことができます。  このトピックでは、配列追加アルゴリズムを使用して、ラムダ、関数オブジェクト、および制限関数の概要を示します。  次の例では、C\+\+ AMP コードを使用しないアルゴリズムを示します。  同じ長さの 2 個の 1 次元配列が作成されます。  対応する整数の要素が加算され、3 番目の 1 次元配列に格納されます。  C\+\+ AMP は使用されません。  
  
```cpp  
  
void CpuMethod() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        sumCPP[idx] = aCPP[idx] + bCPP[idx];  
    }  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        std::cout << sumCPP[idx] << "\n";  
    }  
}  
  
```  
  
## ラムダ式  
 ラムダ式の使用は、C\+\+ AMP を使用してこのコードを記述し直す際に最も直接的な方法です。  
  
```cpp  
  
void AddArraysWithLambda() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    array_view<const int, 1> a(5, aCPP);  
    array_view<const int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(  
        sum.extent,   
        [=](index<1> idx) restrict(amp)  
        {  
            sum[idx] = a[idx] + b[idx];  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 ラムダ式には、1 個のインデックス パラメーターと `restrict(amp)` が含まれている必要があります。  例では、[array\_view](../../parallel/amp/reference/array-view-class.md)`sum` オブジェクトに 1.のランクがあります。  したがって、ラムダ ステートメントに対するパラメーターは、ランクが 1 の[インデックス](../../parallel/amp/reference/index-class.md) オブジェクトです。  実行時には、ラムダ式は [array\_view](../../parallel/amp/reference/array-view-class.md) オブジェクトの各要素に対して 1 回実行されます。  詳細については、「[ラムダ式の構文](../../cpp/lambda-expression-syntax.md)」を参照してください。  
  
## Function オブジェクト  
 アクセラレータ コードを関数オブジェクトに組み込むことができます。  
  
```cpp  
  
class AdditionFunctionObject  
{  
public:  
    AdditionFunctionObject(const array_view<int, 1>& a,  
        const array_view<int, 1>& b,  
        const array_view<int, 1>& sum  
    )  
    : a(a), b(b), sum(sum)  
    {  
    }  
  
    void operator()(index<1> idx) restrict(amp)  
    {  
        sum[idx] = a[idx] + b[idx];  
    }  
  
private:  
    array_view<int, 1> a;  
    array_view<int, 1> b;  
    array_view<int, 1> sum;  
};  
  
void AddArraysWithFunctionObject() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    array_view<const int, 1> a(5, aCPP);  
    array_view<const int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(  
        sum.extent,   
        AdditionFunctionObject(a, b, sum)  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 関数オブジェクトには、コンストラクターと、関数呼び出し演算子のオーバーロードが含まれている必要があります。  関数呼び出し演算子には、1 個のインデックス パラメーターが含まれている必要があります。  関数のオブジェクトのインスタンスは、[parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) メソッドに 2 番目の引数として渡されます。  この例では、3 個の [array\_view](../../parallel/amp/reference/array-view-class.md) オブジェクトが関数オブジェクトのコンストラクターに渡されます。  [array\_view](../../parallel/amp/reference/array-view-class.md)`sum` オブジェクトのランクは 1 です。  したがって、関数呼び出し演算子に対するパラメーターは、ランクが 1 の[インデックス](../../parallel/amp/reference/index-class.md) オブジェクトです。  実行時には、関数は [array\_view](../../parallel/amp/reference/array-view-class.md) オブジェクトの各要素に対して 1 回実行されます。  詳細については、「[関数呼び出し](../Topic/Function%20Call%20\(C++\).md)」および「[STL 内の関数オブジェクト](../../standard-library/function-objects-in-the-stl.md)」を参照してください。  
  
## C\+\+ AMP 制限関数  
 制限関数を作成し、ラムダ式や関数オブジェクトから呼び出すことにより、アクセラレータ コードを組み込むこともできます。  次のコード例では、ラムダ式からの制限関数を呼び出す方法を示します。  
  
```cpp  
  
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)  
{  
    sum[idx] = a[idx] + b[idx];  
}  
  
void AddArraysWithFunction() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    array_view<int, 1> a(5, aCPP);  
    array_view<int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(  
        sum.extent,   
        [=](index<1> idx) restrict(amp)  
        {  
            AddElementsWithRestrictedFunction(idx, sum, a, b);  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 制限関数は、`restrict(amp)` を含んでおり、「[restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)」で説明されている制約に準拠している必要があります。  
  
## 参照  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [ラムダ式の構文](../../cpp/lambda-expression-syntax.md)   
 [関数呼び出し](../Topic/Function%20Call%20\(C++\).md)   
 [STL 内の関数オブジェクト](../../standard-library/function-objects-in-the-stl.md)   
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)