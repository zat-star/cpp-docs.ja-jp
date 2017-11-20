---
title: "&lt;概要&gt;(Visual C) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <summary>
- summary
dev_langs: C++
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a37446278dd1148afe6483f6867f3f8f1332fec4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltsummarygt-visual-c"></a>&lt;概要&gt;(Visual C)
\<summary> タグは、型または型のメンバーの説明に使用します。 型の説明に補足情報を追加するには、[\<remarks>](../ide/remarks-visual-cpp.md) タグを使用します。  
  
## <a name="syntax"></a>構文  
  
```  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `description`  
 オブジェクトの概要。  
  
## <a name="remarks"></a>コメント  
 テキスト、\<概要 > タグは、IntelliSense の入力に関する情報の唯一のソースでありにも表示されます、[オブジェクト ブラウザー](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470)とコード コメントの Web レポート。  
  
 コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。  
  
## <a name="example"></a>例  
  
```  
// xml_summary_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_summary_tag.dll  
  
/// Text for class MyClass.  
public ref class MyClass {  
public:  
   /// <summary>MyMethod is a method in the MyClass class.  
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>  
   /// <seealso cref="MyClass::MyMethod2"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void MyMethod2() {}  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)