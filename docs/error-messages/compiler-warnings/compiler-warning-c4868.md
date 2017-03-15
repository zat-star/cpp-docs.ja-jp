---
title: "コンパイラの警告 C4868 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 26031e1ac6f39d745a772e1becf3f817213a59d8
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4868"></a>コンパイラの警告 C4868
'file(line_number)' コンパイラは中かっこで囲んだ初期化子リストの左から右へ評価順序を強制しない場合があります。  
  
 中かっこで囲んだ初期化子リストの要素では、左から右へ順番に評価されます。 2 つのケースをコンパイラがこの順序を保証することがある:&1; つの値によって渡されるオブジェクトがいくつかの要素の場合は、コンパイルすると、もう&1; つは`/clr`要素の一部は、フィールド オブジェクトのまたは配列要素であるとします。 コンパイラは、左から右へ評価を保証できない場合は、警告 C4868 を出力します。  
  
 この警告は、Visual C 2015 更新プログラム 2 で行ったコンパイラへの準拠作業の結果として生成できます。 Visual C 2015 更新プログラム 2 の前にコンパイルされたコードには、今すぐ C4868 が生成されます。  
  
 既定では、この警告はオフに設定されています。 使用`/Wall`この警告をアクティブにします。  
  
 この警告を解決するには、まず初期化子リストの要素の左から右へ評価が、要素の評価が順序に依存する副次的な影響を生じる可能性があるときなど、必要かどうかを検討します。 多くの場合、要素が評価される順序に目に見える効果はありません。  
  
 評価の順序では、左から右へ、ある必要がある場合は、かどうかは (const) 参照で要素を渡すことを検討します。 この変更は、次のコード サンプルでは警告を排除します。  
  
## <a name="example"></a>例  
 次の例では、C4868 を生成します。  
  
```  
// C4868.cpp  
// compile with: /c /Wall  
#include <cstdio>  
  
class HasCopyConstructor  
{  
public:  
    int x;  
  
    HasCopyConstructor(int x): x(x) {}  
  
    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)  
    {  
        printf("Constructing %d\n", h.x);  
    }  
};  
  
class TripWarning4868  
{  
public:  
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.  
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}  
  
    // This variation will not trigger the warning:  
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}  
};  
  
int main()  
{  
    HasCopyConstructor a{1};  
    HasCopyConstructor b{2};  
  
    // the warning will indicate the below line, the usage of the braced initializer list.  
    TripWarning4868 warningOnThisLine{a, b};  
};  
```
