# v1.0.3

## 简体中文

改善打开或关闭 Discord、Chrome 等应用时，Master 等实体推子意外跳动或与 Windows 音量不同步的问题。新增通道会先取得正确音量再显示在控制器上；普通通道增删不再触发整组推子重发。Windows 暂时读不到音量时，不会将其误当成 0，也不会用旧值打断正在进行的操作。补充推子状态检查和诊断记录，不增加周期性电机重发或人为操作延迟。

下载下方安装包，退出桥接器后覆盖安装即可，原有设置保留。长时间运行中的偶发情况仍会持续跟踪；若再次出现，请记录时间并保留日志。

## English

Improves unexpected Master and other physical-fader movement or stale feedback when apps such as Discord or Chrome open or close. New channels receive the correct volume before appearing on the surface; ordinary channel additions and removals no longer trigger a full fader replay. A temporary Windows volume-read failure is not treated as zero, and stale values cannot interrupt an ongoing gesture. Adds fader-state checks and diagnostics without periodic motor resends or deliberate control latency.

Close the bridge and install over the existing version; your settings are preserved. Intermittent behavior during long sessions remains under observation. If it recurs, note the time and retain the logs.

## 日本語

Discord や Chrome などの起動・終了時に、Master などの実機フェーダーが不意に動いたり、Windows の音量と同期しなくなったりする問題を改善しました。新しいチャンネルには正しい音量を設定してからサーフェスに表示し、通常のチャンネル追加・削除では全フェーダーを再送しません。Windows から音量を一時的に取得できない場合も 0 と誤認せず、古い値で操作中のフェーダーを戻さないようにしました。周期的なモーター再送や意図的な操作遅延を追加せず、状態確認と診断記録を強化しています。

ブリッジを終了してから上書きインストールしてください。設定は引き継がれます。長時間使用時の偶発的な挙動は引き続き確認します。再発した場合は時刻を記録し、ログを保存してください。

The installer and application are currently unsigned. Verify the SHA-256 value shown below after downloading.

`Windows-Fader-Bridge-for-EUCON-v1.0.3-Setup-x64.exe`
SHA-256: `BE991E3242CD638F46CE5571F4366B4FDD36E05A4E795ACDBB3A7232D0FE53EF`

- [User guides / 使用手册 / ユーザーガイド](https://github.com/lindelea/windows-fader-bridge-eucon)
- [Exact source for v1.0.3](https://github.com/lindelea/windows-fader-bridge/tree/windows-eucon-v1.0.3)

---

# v1.0.2

## 简体中文

修复 Windows 音频通道新增、移除或重新排序后，实体控制器上部分推子可能落到底或保持旧位置，而应用界面与 Windows 音量仍然正确的问题。桥接器现在会在通道结构更新完成后，主动将所有保留通道的当前推子及控制状态重新发送给 EUCON。同步会避开正在触摸的推子和尚未完成的控制写入，不会加入周期性刷新，也不会增加操作延迟。

## English

Fixes physical faders that could fall to the bottom or remain at an old position after Windows audio channels were added, removed, or reordered, even though the app and Windows still showed the correct volume. After a channel-list update, the bridge now republishes the current fader and control state for all retained channels to EUCON. Recovery waits for active touches and pending control writes, without periodic refreshes or added control latency.

## 日本語

Windows のオーディオチャンネルが追加・削除・並べ替えされた後、アプリと Windows の音量表示は正しいまま、一部の実機フェーダーが最下部に落ちたり古い位置に残ったりする問題を修正しました。チャンネル構成の更新後、保持されている全チャンネルの現在のフェーダーおよび操作状態を EUCON へ再送します。タッチ中のフェーダーや未完了の操作を避けて同期し、周期的な再送や操作遅延は追加しません。

The installer and application are currently unsigned. Verify the SHA-256 value shown below after downloading.

`Windows-Fader-Bridge-for-EUCON-v1.0.2-Setup-x64.exe`
SHA-256: `9079561CD003BAED95FFD803D551C3A7E04BF7E418FD2187F6310E3C90C54FA0`

---

# v1.0.1

## 简体中文

修复在 UAD 或其他 EUCON 应用保持焦点较长时间后，切回 Windows Fader Bridge 时推子及通道反馈可能没有立即恢复的问题。桥接器现在会在应用重新激活或通道重新可见时，从 Windows 当前状态重新发布推子、声像、静音、独奏、选择、标签及相关反馈；同步会等待正在进行的触摸和控制操作结束，不会增加周期性刷新或控制延迟。同时避免把 EUCON 的强制同步通知误当作用户操作。

## English

Fixes channel feedback that could remain stale after UAD or another EUCON application held focus for an extended period and Windows Fader Bridge became active again. The bridge now republishes current Windows fader, pan, mute, solo, selection, label, and related state when the application is reactivated or its channels become visible. Recovery waits for active touch and control gestures to settle, without adding periodic refreshes or control latency. Forced EUCON synchronization notifications are also prevented from being interpreted as user input.

## 日本語

UAD など別の EUCON アプリを長時間フォーカスした後、Windows Fader Bridge に戻った際にフェーダーやチャンネルのフィードバックが直ちに復元されないことがある問題を修正しました。アプリの再アクティブ化、またはチャンネルの再表示時に、Windows の現在のフェーダー、パン、ミュート、ソロ、選択、ラベルなどの状態を再送します。タッチ中や操作中は完了まで待機し、周期的な再描画や操作遅延は追加しません。また、EUCON の強制同期通知をユーザー操作として誤認しないようにしました。

The installer and application are currently unsigned. Verify the SHA-256 value shown below after downloading.

`Windows-Fader-Bridge-for-EUCON-v1.0.1-Setup-x64.exe`
SHA-256: `0B9F59835552E9FED93AFBE8A0FFBBC2D552DAD6FFFCF3AEF9BE464B3E51B48E`

---

# v1.0.0

## 简体中文

首个面向用户的正式版本。提供 Windows 11 x64 安装程序、中英双语应用界面、中英日三语使用手册，以及 Windows 音频与 EUCON 的实时双向控制。已在 Avid S3 与 Avid Control 上验证。开机时 Windows Audio 或 EUCON 尚未就绪，程序会自动等待并重连。

## English

First public user release. Includes a Windows 11 x64 installer, English/Chinese app UI, English/Chinese/Japanese guides, and real-time bidirectional Windows Audio/EUCON control. Verified with Avid S3 and Avid Control. The bridge now waits and reconnects automatically when Windows Audio or EUCON starts late during sign-in.

## 日本語

一般ユーザー向け初回正式リリースです。Windows 11 x64 インストーラー、中英対応アプリ画面、中英日ユーザーガイド、Windows Audio と EUCON のリアルタイム双方向操作を収録しています。Avid S3 と Avid Control で確認済みです。サインイン時に Windows Audio または EUCON の起動が遅れても、自動的に待機・再接続します。

The installer and application are currently unsigned. Verify the SHA-256 value shown below after downloading.

`Windows-Fader-Bridge-for-EUCON-v1.0.0-Setup-x64.exe`  
SHA-256: `8C822D5B5ECDD481B0B3B597378EBE0BE459E646A9A092B30BA1AE8135FF7257`
