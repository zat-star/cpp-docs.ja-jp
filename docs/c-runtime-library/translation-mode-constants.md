---
title: "変換モード定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _O_BINARY
- _O_TEXT
- _O_RAW
dev_langs: C++
helpviewer_keywords:
- O_BINARY constant
- O_TEXT constant
- O_RAW constant
- _O_TEXT constant
- _O_RAW constant
- translation constants
- _O_BINARY constant
- translation, constants
- translation, modes
- translation modes (file I/O)
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8f5224064158dcbcb277524af21a0059a324fbc5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="translation-mode-constants"></a>変換モード定数
## <a name="syntax"></a>構文  
  
```  
  
#include <fcntl.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 マニフェスト定数の `_O_BINARY` と `_O_TEXT` により、ファイルの変換モード (`_open` と `_sopen`) またはストリームの変換モード (`_setmode`) が決定されます。  
  
 有効な値は以下のものがあります。  
  
 `_O_TEXT`  
 ファイルをテキスト (変換) モードで開きます。 キャリッジ リターンとラインフィード (CR-LF) の組み合わせは、入力時に 1 つのラインフィード (LF) に変換されます。 ラインフィード文字は、出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取りまたは読み取り/書き込み用にファイルを開いた場合、`fopen` はファイル末尾に Ctrl + Z があるかどうかを確認し、それを削除できる場合は削除します。 この処理が行われる理由は、CTRL+Z で終わるファイルの中身を `fseek` 関数および `ftell` 関数で移動するとき、ファイル末尾付近で `fseek` が正しく動作しないことがあるためです。  
  
 `_O_BINARY`  
 ファイルをバイナリ (無変換) モードで開きます。 上の変換は行われません。  
  
 `_O_RAW`  
 `_O_BINARY` と同じ。 C 2.0 互換性のためにサポート。  
  
 詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[File Translation](../c-runtime-library/file-translation-constants.md)」 (ファイル変換) を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [_open、_wopen](../c-runtime-library/reference/open-wopen.md)   
 [_pipe](../c-runtime-library/reference/pipe.md)   
 [_sopen、_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_setmode](../c-runtime-library/reference/setmode.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)