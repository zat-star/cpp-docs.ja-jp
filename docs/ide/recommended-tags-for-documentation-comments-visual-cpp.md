---
title: "ドキュメント コメント (Visual C) 用の推奨タグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c1b0e762ec2167a988e8e18f3dce932214716c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>ドキュメント コメントとして推奨されるタグ (Visual C++)
Visual C コンパイラがコード内のドキュメントのコメントが処理され、各コンパイル単位の .xdc ファイルを作成し、xdcmake.exe は .xml ファイルに .xdc ファイルを処理します。 サイトで実装する必要がある詳細は、ドキュメントを作成する .xml ファイルを処理します。  
  
 タグは、型などの構造上で処理され、メンバーを入力します。  
  
 型またはメンバー タグの直前にある必要があります。  
  
> [!NOTE]
>  ドキュメント コメントは適用できませんを名前空間またはプロパティとイベントの定義は行外ドキュメント コメントは、クラスの宣言でする必要があります。  
  
 コンパイラは、有効な XML のタグをすべて処理します。 次のタグは、ユーザー ドキュメントでよく使用される機能を提供します。  
  
||||  
|-|-|-|  
|[\<c>](../ide/c-visual-cpp.md)|[\<code>](../ide/code-visual-cpp.md)|[\<example>](../ide/example-visual-cpp.md)|  
|[\<例外 >](../ide/exception-visual-cpp.md)1|[\<含める >](../ide/include-visual-cpp.md)1|[\<list>](../ide/list-visual-cpp.md)|  
|[\<para>](../ide/para-visual-cpp.md)|[\<param >](../ide/param-visual-cpp.md)1|[\<paramref >](../ide/paramref-visual-cpp.md)1|  
|[\<アクセス許可 >](../ide/permission-visual-cpp.md)1|[\<remarks>](../ide/remarks-visual-cpp.md)|[\<returns>](../ide/returns-visual-cpp.md)|  
|[\<参照してください >](../ide/see-visual-cpp.md)1|[\<seealso >](../ide/seealso-visual-cpp.md)1|[\<summary>](../ide/summary-visual-cpp.md)|  
|[\<value>](../ide/value-visual-cpp.md)|||  
  
 1. コンパイラでは、構文を確認します。  
  
 現在のリリースでは、Visual C コンパイラがサポートされていません`<paramref>`、他の Visual Studio コンパイラでサポートされているタグ。 Visual C サポート`<paramref>`将来のリリースでします。  
  
## <a name="see-also"></a>参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)