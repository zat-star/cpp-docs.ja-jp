---
title: "ストリームの制御 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Controlling Streams
dev_langs:
- C++
helpviewer_keywords:
- streams, controlling
- controlling streams
- streams
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: d2211a2a2bb5121921928166626d726db8dea67f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="controlling-streams"></a>ストリームの制御
[fopen](../c-runtime-library/reference/fopen-wfopen.md) は `FILE` 型のオブジェクトのアドレスを返します。 いくつかのライブラリ関数の引数 `stream` としてこのアドレスを使用し、開かれたファイルに対してさまざまな操作を実行します。 バイト ストリームについては、[fgetc](../c-runtime-library/reference/fgetc-fgetwc.md) を呼び出して各文字を読み取るかのようにすべての入力が処理され、[fputc](../c-runtime-library/reference/fputc-fputwc.md) を呼び出して各文字を書き込むかのようにすべての出力が処理されます。 ワイド ストリームについては、[fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md) を呼び出して各文字を読み取るかのようにすべての入力が処理され、[fputwc](../c-runtime-library/reference/fputc-fputwc.md) を呼び出して各文字を書き込むかのようにすべての出力が処理されます。  
  
 [fclose](../c-runtime-library/reference/fclose-fcloseall.md) を呼び出すとファイルを閉じることができ、そのあと `FILE` オブジェクトのアドレスは無効になります。  
  
 `FILE` オブジェクトは次のようなストリームの状態を格納します。  
  
-   関数が読み取りまたは書き込みのエラーを検出すると 0 以外に設定されるエラー インジケーター。  
  
-   関数が読み取り中にファイルの終端を検出すると 0 以外に設定される EOF インジケーター。  
  
-   ストリーム内で次に読み取るまたは書き込むバイトを指定するファイル位置インジケーター (ファイルが位置決め要求をサポートしている場合)。  
  
-   ストリームで読み取りまたは書き込み (あるいはその両方) を承認するかどうか、ストリームが非バインド、バイト指向、ワイド指向のいずれであるかを指定する[ストリームの状態](../c-runtime-library/stream-states.md)。  
  
-   一部がアセンブルされた、または生成済みである汎用マルチバイト文字の状態、およびファイル内のバイト シーケンスのシフト状態を記憶する変換の状態。  
  
-   ライブラリ関数がストリームの読み取りまたは書き込みのパフォーマンス改善に使用できる配列オブジェクトのアドレスおよびサイズを指定するファイル バッファー。  
  
 `FILE` オブジェクト、またはそのオブジェクトと使用するために指定したファイル バッファーに格納されている値は変更しないでください。 `FILE` オブジェクトをコピーすること、およびそのコピーのアドレスをライブラリ関数への引数 `stream` として移植して使用することはできません。  
  
## <a name="see-also"></a>関連項目  
 [ファイルとストリーム](../c-runtime-library/files-and-streams.md)
