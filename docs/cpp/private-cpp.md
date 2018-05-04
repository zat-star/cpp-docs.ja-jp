---
title: プライベート (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- private_cpp
dev_langs:
- C++
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb0b8c748a3cf92faae451ab024d5592bb24b47
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="private-c"></a>private (C++)
## <a name="syntax"></a>構文  
  
```  
private:  
   [member-list]  
private base-class  
```  
  
## <a name="remarks"></a>コメント  
 クラス メンバーのリストを前に置くと、`private` キーワードは、それらのメンバーがクラスのメンバー関数およびフレンドからのみアクセスできることを指定します。 これは、次のアクセス指定子またはクラスの末尾までで宣言されているすべてのメンバーに適用されます。  
  
 基底クラスの名前を指定すると、`private` キーワードは、基底クラスのパブリック、プロテクト メンバーが派生クラスのプライベート メンバーであることを指定します。  
  
 クラスのメンバーの既定のアクセスはプライベートです。 構造体または共用体のメンバーの既定のアクセスはパブリックです。  
  
 基底クラスの既定のアクセスは、クラスの場合はプライベートで、構造体の場合はパブリックです。 共用体に基底クラスを設定することはできません。  
  
 関連情報については、次を参照してください[フレンド](../cpp/friend-cpp.md)、[パブリック](../cpp/public-cpp.md)、[保護](../cpp/protected-cpp.md)、とでメンバー アクセス テーブル[クラス メンバーへのアクセスの制御](member-access-control-cpp.md).  
  
## <a name="clr-specific"></a>/clr 固有  
 CLR 型では、C++ アクセス指定子のキーワード (**パブリック**、 `private`、および`protected`) 型とアセンブリに関連メソッドの可視性に影響を与えることができます。 詳細については、次を参照してください。[メンバー アクセス コントロール](member-access-control-cpp.md)です。  
  
> [!NOTE]
>  コンパイルされるファイル[/LN](../build/reference/ln-create-msil-module.md)この動作の影響は受けません。 この場合、すべてのマネージ クラス (パブリックかプライベート) が表示されます。  
  
## <a name="end-clr-specific"></a>END /clr 固有  
  
## <a name="example"></a>例  
  
```  
// keyword_private.cpp  
class BaseClass {  
public:  
   // privMem accessible from member function  
   int pubFunc() { return privMem; }  
private:  
   void privMem;  
};  
  
class DerivedClass : public BaseClass {  
public:  
   void usePrivate( int i )  
      { privMem = i; }   // C2248: privMem not accessible  
                         // from derived class  
};  
  
class DerivedClass2 : private BaseClass {  
public:  
   // pubFunc() accessible from derived class  
   int usePublic() { return pubFunc(); }  
};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   DerivedClass2 aDerived2;  
   aBase.privMem = 1;     // C2248: privMem not accessible  
   aDerived.privMem = 1;  // C2248: privMem not accessible  
                          //    in derived class  
   aDerived2.pubFunc();   // C2247: pubFunc() is private in  
                          //    derived class  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス メンバーへのアクセスを制御します。](member-access-control-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)