---
title: "環境名 |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: efae64f64ef6b5ed92dffafb9f83a0e32ab38513
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="environment-names"></a>環境名
**ANSI 4.10.4.4** [getenv](../c-runtime-library/reference/getenv-wgetenv.md) 関数が使用する環境名の設定と環境の一覧を変更するためのメソッド  
  
 環境名のセットは無制限です。  
  
 C プログラム内から環境変数を変更するには、[_putenv](../c-runtime-library/reference/putenv-wputenv.md) 関数を呼び出します。 Windows のコマンド ラインから環境変数を変更するには、SET コマンドを使用します (たとえば、SET LIB = D:\ LIBS)。  
  
 C プログラム内部から設定されている環境変数は、オペレーティング システム コマンド シェルのその変数のホスト コピーが実行されている間だけ存在します (CMD.EXE または COMMAND.COM)。 たとえば、次の関数を呼び出します。  
  
```  
system( SET LIB = D:\LIBS );  
```  
  
 はコマンド シェル (CMD.EXE) のコピーを実行し、環境変数 LIB を設定し、CMD.EXE のセカンダリ コピーを終了して、C プログラムに戻ります。 CMD.EXE のそのコピーを終了すると、一時的な環境変数 LIB が削除されます。  
  
 同様に、`_putenv` 関数によって行われた変更はプログラムが終了するまで継続します。  
  
## <a name="see-also"></a>参照  
 [ライブラリ関数](../c-language/library-functions.md)   
 [_putenv、_wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [getenv、 _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)