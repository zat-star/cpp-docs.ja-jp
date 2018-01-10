---
title: "-SECTION (EDITBIN) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /section
dev_langs: C++
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91ffb9bd0645cab51e4140697c41e5b715380fe8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)
```  
/SECTION:name[=newname][,attributes][alignment]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、セクションのオブジェクト ファイルがコンパイルまたはリンク時に設定された属性をオーバーライドするセクションの属性を変更します。  
  
 コロンの後に ( **:** )、指定、*名前*セクションのです。 次のセクションの名前を変更する*名前*は等号 (=) でと*newname*セクションのです。  
  
 設定または変更するセクションの`attributes`、コンマ区切り (**、**) 1 つまたは複数の属性の英文字で構成します。 属性を符号反転するには、感嘆符 (!) 付きの文字の前にします。 次の文字は、メモリの属性を指定します。  
  
|属性|設定|  
|---------------|-------------|  
|c|code|  
|d|破棄可能|  
|e|executable|  
|i|初期化されたデータ|  
|k|仮想メモリのキャッシュ|  
|m|リンクを削除します。|  
|o|リンク情報|  
|p|仮想メモリのページング|  
|r|読み取り|  
|s|shared|  
|u|初期化されていないデータ|  
|週|書き込み|  
  
 コントロールに*配置*、文字を指定**A**後に、次の文字を次のように、(バイト単位) の配置のサイズを設定する 1 つ。  
  
|文字|配置のサイズ (バイト単位)|  
|---------------|-----------------------------|  
|1|1|  
|2|2|  
|4|4|  
|9|8|  
|p|16|  
|t|32|  
|秒|64|  
|x|位置合わせなし|  
  
 指定、`attributes`と*配置*文字として空白を含む文字列。 文字では大文字小文字が区別されません。  
  
## <a name="see-also"></a>参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)