---
title: "配列の初期化 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列の初期化"
  - "初期化の配列 [C++]"
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 配列の初期化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスにコンストラクターがある場合、そのクラスの配列はコンストラクターによって初期化されます。 配列の要素よりも初期化子リスト内の項目が少ない場合、残りの要素には既定のコンストラクターが使用されます。 クラスに対して既定のコンストラクターが定義されていない場合は、完全な初期化子リストが必要です。つまり、配列の各要素に 1 つずつ初期化子が必要です。  
  
 2 つのコンストラクターを定義する `Point` クラスを考えます。  
  
```  
// initializing_arrays1.cpp  
class Point  
{  
public:  
   Point()   // Default constructor.  
   {  
   }  
   Point( int, int )   // Construct from two ints  
   {  
   }  
};  
  
// An array of Point objects can be declared as follows:  
Point aPoint[3] = {  
   Point( 3, 3 )     // Use int, int constructor.  
};  
  
int main()  
{  
}  
```  
  
 `aPoint` の最初の要素はコンストラクター `Point( int, int )` を使用して構築されます。残りの 2 つの要素は既定のコンストラクターを使用して構築されます。  
  
 静的メンバー配列 (かどうか **const** またはない) (、クラス宣言の外側) 定義内で初期化できます。 例:  
  
```  
// initializing_arrays2.cpp  
class WindowColors  
{  
public:  
    static const char *rgszWindowPartList[7];  
};  
  
const char *WindowColors::rgszWindowPartList[7] = {  
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",  
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [(NOTINBUILD)特殊なメンバー関数](http://msdn.microsoft.com/ja-jp/82223d73-64cb-4923-b678-78f9568ff3ca)