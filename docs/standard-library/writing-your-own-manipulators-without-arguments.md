---
title: "引数を使用しない独自マニピュレーターの作成 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c7439908970d61f55f10915ff69bc990a6fcc841
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="writing-your-own-manipulators-without-arguments"></a>引数を使用しない独自マニピュレーターの作成
引数を使用しないマニピュレーターを作成するには、クラスを派生させる必要も、複雑なマクロを使う必要もありません。 たとえば、プリンターを太字モードにするために、\<ESC>[ のペアが必要であるとします。 このペアは、次のようにして、ストリームに直接挿入できます。  
  
```  
cout <<"regular " <<'\033' <<'[' <<"boldface" <<endl;  
```  
  
 または、次のように `bold` マニピュレーターを定義して、文字を挿入することもできます。  
  
```  
ostream& bold(ostream& os) {  
    return os <<'\033' <<'[';  
}  
cout <<"regular " <<bold <<"boldface" <<endl;  
```  
  
 グローバルに定義された `bold` 関数は、引数として `ostream` の参照をとり、`ostream` の参照を返します。 この関数は、プライベート クラス要素にアクセスする必要がないため、メンバー関数でもフレンド関数でもありません。 `bold` 関数は、ストリームの `<<` 演算子がその型の関数を受け付けるようにオーバーロードされているため、次のような宣言を使用してストリームに接続します。  
  
```  
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))  
{     // call ios_base manipulator  
 (*_Pfn)(*(ios_base *)this);

    return (*this);

}  
```  
  
 この機能を使うと、その他のオーバーロードされた演算子を拡張することができます。 この場合、`bold` がストリームに文字を挿入することは付随的な事柄です。 この関数は、関数がストリームに挿入された時点で呼び出されます。これは、必ずしも隣接する文字が印刷される時点ではありません。 したがって、ストリームのバッファリングの影響で、印刷が遅れる可能性があります。  
  
## <a name="see-also"></a>参照  
 [出力ストリーム](../standard-library/output-streams.md)

