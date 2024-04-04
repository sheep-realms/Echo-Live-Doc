# 配置文件数据版本历史

## 3（1.3.0~至今）
**新增：**

- `global`：
    - `theme`、`theme_script_enable`、`color_scheme`。
- `history`：
    - `history_theme`、`history_theme_script_enable`。

## 2（1.3.0-snapshot-24w09a）
**新增：**

- `global`：
    - `language`。
- `echolive`：
    - `websocket_reconnect_limit`、`sleep_during_printing_stop_print`。
- `history`：
    - `message_list_reverse`、`message_item_reverse`、`display_username`、`display_time`、`remove_continuous_duplicate`、`latest_message_hide`。
- `accessible`：
    - `high_contrast_outline_color`、`high_contrast_outline_size`、`high_contrast_outline_style`。
- `advanced`：
    - `broadcast`：
        - `allow_name_duplicate`。

## 1（~1.2.7）
**新增：**

- `data_version`；
- `echo.print_speed`；
- `echolive`：
    - `live_theme`、`live_theme_script_enable`、`broadcast_enable`、`broadcast_channel`、`websocket_enable`、`websocket_url`、`experimental_api_enable`、`messages_polling_enable`、`messages_polling_tick`、`sleep_enable`、`print_audio_enable`、`print_audio_name`、`print_audio_volume`、`print_audio_rate`、`next_audio_enable`、`next_audio_name`、`next_audio_volume`、`next_audio_rate`；
- `editor`：
    - `tabpage_config_enable`、`tabpage_output_enable`、`client_state_panel_enable`、`username_init`、`output_before`、`ontput_before_enable`、`output_after`、`ontput_after_enable`、`history_resend_bubble`、`history_maximum`、`log_line_maximum`、`palette`、`palette_color_contrast_enable`、`palette_color_contrast_background_color`、`palette_color_contrast_threshold`
- `accessible`：
    - `high_contrast`、`drotanopia_and_deuteranopia`；
- `advanced`：
    - `editor`：
        - `history_minimum_breaker_threshold`。

**新增保留：**

- `echolive`：
    - `next_effect_name`、`next_effect_duration`、`print_effect_name`、`print_effect_duration`、`print_start_effect_name`、`print_start_effect_duration`、`print_end_effect_name`、`print_end_effect_duration`；
- `history`、`selector`、`character`。