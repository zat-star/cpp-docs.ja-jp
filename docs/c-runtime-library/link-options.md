---
title: "リンク オプション | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
- loosefpmath.obj
- smallheap.obj
- fp10.obj
- nochkclr.obj
- chkstk.obj
- pcommode.obj
- pnoenv.obj
- link options [C++]
- invalidcontinue.obj
- pnothrownew.obj
- pwsetargv.obj
- pinvalidcontinue.obj
- wsetargv.obj
- binmode.obj
- setargv.obj
- noarg.obj
- pnewmode.obj
- commode.obj
- pthreadlocale.obj
- pbinmode.obj
- threadlocale.obj
- pnoarg.obj
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ece67a7c2b50423ea9ff4610e638dcdc2b979e14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="link-options"></a>リンク オプション
CRT lib ディレクトリには、コード変更を加えずに特定の CRT 機能を有効にする複数のオブジェクト ファイルが含まれます。 これらは、リンカー コマンド ラインに追加するだけで使用することができるため、「リンク オプション」と呼ばれます。  
  
 ピュア モード バージョンは存在しますが、Visual Studio 2015 では使用されていません。 ネイティブおよび /clr コードには標準のバージョン、/clr:pure モードにはピュア バージョン (プレフィックスは a p) を使用します。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
|ネイティブおよび /clr|ピュア モード|説明|  
|----------------------|---------------|-----------------|  
|binmode.obj|pbinmode.obj|既定のファイルの変換モードをバイナリに設定します。 [_fmode](../c-runtime-library/fmode.md) をご覧ください。|  
|chkstk.obj|N/A|CRT を使用していない場合にスタック チェックと alloca サポートを提供します。|  
|commode.obj|pcommode.obj|グローバル コミット フラグを "コミット" に設定します。 [fopen、_wfopen](../c-runtime-library/reference/fopen-wfopen.md) および [fopen_s、_wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) をご覧ください。|  
|fp10.obj|N/A|既定の精度制御を 64 ビットに変更します。 「[浮動小数点サポート](../c-runtime-library/floating-point-support.md)」をご覧ください。|  
|invalidcontinue.obj|pinvalidcontinue.obj|何もしない既定の無効なパラメーター ハンドラーを設定します。つまり、CRT 関数に渡される無効なパラメーターによってエラー番号が設定され、エラーの結果が返されます。|  
|loosefpmath.obj|N/A|浮動小数点コードが非正規化値を許容するようにします。|  
|newmode.obj|pnewmode.obj|失敗時に [malloc](../c-runtime-library/reference/malloc.md) が新しいハンドラーを呼び出すようにします。 [_set_new_mode](../c-runtime-library/reference/set-new-mode.md)、[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)、[calloc](../c-runtime-library/reference/calloc.md)、[realloc](../c-runtime-library/reference/realloc.md) をご覧ください。|  
|noarg.obj|pnoarg.obj|argc および argv のすべてのプロセスを無効にします。|  
|nochkclr.obj|N/A|処理を行いません。 プロジェクトから削除してください。|  
|noenv.obj|pnoenv.obj|CRT のキャッシュ済み環境の作成を無効にします。|  
|nothrownew.obj|pnothrownew.obj|CRT で new のスローしないバージョンを有効にします。 「[new および delete 演算子](../cpp/new-and-delete-operators.md)」をご覧ください。|  
|setargv.obj|psetargv.obj|コマンド ライン引数のワイルドカードの展開を有効にします。 「[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」をご覧ください。|  
|threadlocale.obj|pthreadlocale.obj|既定ですべての新しいスレッドに対してスレッド単位のロケールを有効にします。|  
|wsetargv.obj|pwsetargv.obj|コマンド ライン引数のワイルドカードの展開を有効にします。 「[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」をご覧ください。|  
  
## <a name="see-also"></a>参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)