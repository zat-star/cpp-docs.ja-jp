---
title: "引数を使用しない独自マニピュレーターの作成 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 276bba3dd5ce5debd926ebbc4ccfaf52c6b92097
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

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
  
## <a name="see-also"></a>関連項目  
 [出力ストリーム](../standard-library/output-streams.md)


