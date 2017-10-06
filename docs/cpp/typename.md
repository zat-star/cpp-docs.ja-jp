---
title: "typename |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- typename_cpp
dev_langs:
- C++
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 95283efc5d3b92a461ba6507e669f6f3e2af2689
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="typename"></a>typename
テンプレート定義で不明な識別子が型である、コンパイラにヒントを提供します。 型パラメーターを指定するには、テンプレート パラメーター リストでは使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
typename identifier;  
```  
  
## <a name="remarks"></a>コメント  
 テンプレートの定義で名前が、テンプレート引数に依存する修飾名である場合、このキーワードを使用する必要があります。修飾名が依存していない場合は省略可能です。 詳細については、次を参照してください。[テンプレートと名前解決](../cpp/templates-and-name-resolution.md)です。  
  
 **typename**テンプレート宣言または定義で任意の場所の任意の型で使用できます。 テンプレート基底クラスへのテンプレート引数として使用する場合を除いて、このキーワードを基底クラス リストで使用することはできません。  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 **Typename**の代わりにキーワードを使用することも**クラス**テンプレート パラメーター リストでします。 たとえば、次のステートメントは、同じ意味は。  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>例  
  
```  
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [テンプレート](../cpp/templates-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)
