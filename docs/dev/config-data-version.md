# 配置文件数据版本历史

## 10（1.5.5~至今）

**新增：**

- `editor`：
    - `websocket`：
        - `enable`、`url`、`auto_url`、`reconnect_limit`。
- `advanced`：
    - `performance`：
        - `foreach_text_style_by_message_data`、`row_search_threshold`。
    - `device`：
        - `enable`。

**移动：**

- `accessible` 移动至 `accessibility`，其中：
    - `drotanopia_and_deuteranopia` 移动至 `protanopia_and_deuteranopia`。

## 9（1.5.4）

**新增：**

- `global`：
    - `touchscreen_layout`、`thin_scrollbar`。
- `echolive`：
    - `layout`：
        - `username_text_align_right`、`diplay_controller`。
- `accessible`：
    - `font_size`、`unlock_page_width`。

## 8（1.5.3）

**新增：**

- `advanced`：
    - `broadcast`：
        - `allow_send_duplicate_message`。
    - `settings`：
        - `display_hidden_option`。

## 7（1.5.0~1.5.2）

**新增：**

- `echolive`：
    - `print_effect`：
        - `name`、`duration`、`scale`、`timing_function`。
- `history`：
    - `message`：
        - `live_display_hidden_latest_message_show`。

## 6（1.4.7）

**新增：**

- `global`：
    - `global.controller_layout_reverse`。
- `advanced`：
    - `settings`：
        - `display_config_key`、`speech_synthesis_voices_maximum`。

## 5（1.4.3~1.4.6）
**新增：**

- `echolive`：
    - `display`：
        - `auto`、`hidden_wait_time`、`long_text_compensation_rate`、`hidden_time`、`show_time`。

## 4（1.4.0~1.4.2）
**新增：**

- `echolive`：
    - `speech_synthesis`：
        - `voice`、`pitch`、`rate`、`delay`、`speech_emoji`、`ignored_characters`。
    - `image`：
        - `enable`、`allow_data_url_and_relative_url`、`default_max_size`。
- `editor`：
    - `function`：
        - `images_cache_maximum`。
    - `form`：
        - `quote_before`、`quote_after`。
    - `emoji_picker`：
        - `emoji`。
- `accessible`：
    - `link_underline`、`animation_disable`、`power_saving_mode`。
- `advanced`：
    - `editor`：
        - `forced_display_split_message`。

**移动：**

- `echolive`：
  - `live_theme`、`live_theme_script_enable` 移动至 `style`。
  - `broadcast_enable`、`broadcast_channel` 移动至 `broadcast` 并分别更名为 `enable`、`channel`。
  - `websocket_enable`、`websocket_url`、`websocket_reconnect_limit`、`experimental_api_enable` 移动至 `broadcast`。
  - `messages_polling_enable`、`messages_polling_tick` 移动至 `messages_polling` 并分别更名为 `enable`、`tick`。
  - `sleep_enable`、`sleep_during_printing_stop_print` 移动至 `sleep` 并分别更名为 `enable`、`during_printing_stop_print`。
  - `print_audio_enable`、`print_audio_name`、`print_audio_volume`、`print_audio_rate` 移动至 `print_audio` 并分别更名为 `enable`、`name`、`volume`、`rate`。
  - `next_audio_enable`、`next_audio_name`、`next_audio_volume`、`next_audio_rate` 移动至 `next_audio` 并分别更名为 `enable`、`name`、`volume`、`rate`。
- `editor`：
  - `tabpage_config_enable`、`tabpage_output_enable`、`client_state_panel_enable`、`history_resend_bubble`、`history_maximum`、`log_line_maximum` 移动至 `function`。
  - `username_init` 移动至 `form` 并更名为 `username`。
  - `ontput_before_enable`、`output_before`、`ontput_after_enable`、`output_after` 移动至 `form`。
  - `palette` 移动至 `color_picker`。
  - `palette_color_contrast_enable`、`palette_color_contrast_background_color`、`palette_color_contrast_threshold` 移动至 `color_picker` 并分别更名为 `contrast_enable`、`contrast_background_color`、`contrast_threshold`。
- `history`：
  - `history_theme`、`history_theme_script_enable` 移动至 `style`。
  - `message_list_reverse`、`message_item_reverse`、`display_username`、`display_time` 移动至 `layout`。
  - `remove_continuous_duplicate`、`latest_message_hide` 移动至 `message`。

## 3（1.3.0~1.3.3）
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