# FastBite Group - UI Layout Specification

## 📋 Tổng quan dự án
**FastBite Group** là một nền tảng cộng tác nhóm và quản lý dự án với giao diện hiện đại, responsive và thân thiện người dùng.

## 🎨 Thiết kế tổng thể

### Color Scheme
- **Primary Colors**: 
  - `#ad46ff` (Tím chính)
  - `#1447e6` (Xanh dương)
- **Background**: 
  - Light mode: `#ffffff`, `#f9fafb`, `#f3f4f6`
  - Dark mode: `#111827`, `#1f2937`, `#374151`
- **Text**: 
  - Light mode: `#111827`, `#374151`, `#6b7280`
  - Dark mode: `#f9fafb`, `#d1d5db`, `#9ca3af`

### Typography
- **Font Family**: Inter, system-ui, sans-serif
- **Heading Sizes**: 
  - H1: `text-3xl` (30px)
  - H2: `text-2xl` (24px) 
  - H3: `text-xl` (20px)
  - H4: `text-lg` (18px)
- **Body Text**: `text-base` (16px), `text-sm` (14px), `text-xs` (12px)

### Spacing System
- **Padding**: `p-2`, `p-3`, `p-4`, `p-6`, `p-8`
- **Margin**: `m-2`, `m-3`, `m-4`, `m-6`, `m-8`
- **Gap**: `gap-2`, `gap-3`, `gap-4`, `gap-6`
- **Border Radius**: `rounded-lg`, `rounded-xl`, `rounded-2xl`

## 🏗️ Cấu trúc layout chính

### 1. Root Layout (`/app/layout.tsx`)
```
┌─────────────────────────────────────────────────────────┐
│                    Browser Header                       │
├─────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────────────────────────┐  │
│  │   Sidebar   │  │         Main Content            │  │
│  │  (Collapsed)│  │                                 │  │
│  │             │  │                                 │  │
│  │             │  │                                 │  │
│  │             │  │                                 │  │
│  └─────────────┘  └─────────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
```

### 2. Customer Layout (`/app/(customer)/layout.tsx`)
- **Sidebar**: Cố định bên trái, chiều rộng 96px (`w-24`)
- **Main Content**: Chiếm phần còn lại của màn hình
- **Responsive**: Sidebar có thể ẩn/hiện trên mobile

## 🧭 Sidebar Navigation (Collapsed)

### Logo Section (Top)
```
┌─────────────────┐
│  ┌───────────┐  │
│  │     FB    │  │  ← Logo "FB" trong circle gradient
│  │           │  │     Background: from-[#ad46ff] to-[#1447e6]
│  └───────────┘  │     Size: 48x48px, rounded-2xl
└─────────────────┘
```

### Navigation Icons
```
┌─────────────────┐
│  ┌───────────┐  │  ← MessageCircle (Cá nhân)
│  │     💬    │  │     Active: bg-[#ad46ff], text-white
│  └───────────┘  │     Inactive: hover:bg-gray-100
├─────────────────┤
│  ┌───────────┐  │  ← Compass (Khám phá)
│  │     🧭    │  │     Size: 56x56px (h-14)
│  └───────────┘  │     Rounded: rounded-xl
├─────────────────┤
│  ┌───────────┐  │  ← FileText (Bài đăng)
│  │     📄    │  │     Transition: duration-300
│  └───────────┘  │
├─────────────────┤
│  ┌───────────┐  │  ← User (Hồ sơ)
│  │     👤    │  │
│  └───────────┘  │
└─────────────────┘
```

### Bottom Controls
```
┌─────────────────┐
│  ┌───────────┐  │  ← Theme Toggle (Sun/Moon)
│  │     ☀️    │  │     Size: 32x32px (h-8 w-8)
│  └───────────┘  │     Background: gradient với opacity
├─────────────────┤
│  ┌───────────┐  │  ← Notification Bell
│  │     🔔    │  │     Hover: scale-105
│  └───────────┘  │
├─────────────────┤
│  ┌───────────┐  │  ← User Navigation
│  │     👤    │  │     Avatar hoặc initials
│  └───────────┘  │
└─────────────────┘
```

## 💬 Chat Page (`/chat`)

### Layout 2 cột
```
┌─────────────────────────────────────────────────────────┐
│  ┌─────────────┐  ┌─────────────────────────────────┐  │
│  │ Chat Sidebar│  │        Chat Interface           │  │
│  │   (320px)   │  │                                 │  │
│  │             │  │                                 │  │
│  │             │  │                                 │  │
│  │             │  │                                 │  │
│  └─────────────┘  └─────────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
```

### Chat Sidebar (Left Column)
#### Header
```
┌─────────────────────────────────────────────────┐
│  Trò chuyện                    [Search +]      │
│  0 nhóm đã tham gia                            │
├─────────────────────────────────────────────────┤
│  🔍 Tìm kiếm...                               │
└─────────────────────────────────────────────────┘
```

#### Tabs
```
┌─────────────────────────────────────────────────┐
│  [Cá nhân] [Nhóm]                             │
├─────────────────────────────────────────────────┤
│                                                 │
│  ┌─────────────────────────────────────────────┐ │
│  │  👤 Không có cuộc trò chuyện nào           │ │
│  │     Tìm kiếm người để bắt đầu trò chuyện   │ │
│  └─────────────────────────────────────────────┘ │
│                                                 │
└─────────────────────────────────────────────────┘
```

### Chat Interface (Right Column)
#### Empty State
```
┌─────────────────────────────────────────────────┐
│                                                 │
│                                                 │
│                                                 │
│              💬                                │
│        Chào mừng đến với FastBite Chat         │
│  Chọn một cuộc trò chuyện từ danh sách bên trái│
│                                                 │
│  • Trò chuyện cá nhân                          │
│  • Trò chuyện nhóm                             │
│                                                 │
└─────────────────────────────────────────────────┘
```

#### Active Chat State
```
┌─────────────────────────────────────────────────┐
│  👤 Tên người dùng                    [Menu]  │
│     Trực tuyến                                 │
├─────────────────────────────────────────────────┤
│                                                 │
│  ┌─────────────────────────────────────────────┐ │
│  │  [Message List]                            │ │
│  │                                             │ │
│  │                                             │ │
│  └─────────────────────────────────────────────┘ │
│                                                 │
├─────────────────────────────────────────────────┤
│  [File] [📎] [Message Input] [Send]           │
└─────────────────────────────────────────────────┘
```

## 🔍 Discover Page (`/discover`)

### Layout 2 cột
```
┌─────────────────────────────────────────────────────────┐
│  ┌─────────────┐  ┌─────────────────────────────────┐  │
│  │ My Groups   │  │        Discover Groups          │  │
│  │  (320px)    │  │                                 │  │
│  │             │  │                                 │  │
│  │             │  │                                 │  │
│  │             │  │                                 │  │
│  └─────────────┘  └─────────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
```

### My Groups Sidebar (Left Column)
#### Header
```
┌─────────────────────────────────────────────────┐
│  Nhóm của tôi                                  │
│  0 nhóm đã tham gia                            │
├─────────────────────────────────────────────────┤
│                                                 │
│  ┌─────────────────────────────────────────────┐ │
│  │  👥 Chưa tham gia nhóm nào                 │ │
│  │     Khám phá và tham gia nhóm mới          │ │
│  └─────────────────────────────────────────────┘ │
│                                                 │
└─────────────────────────────────────────────────┘
```

#### Group List Item (when groups exist)
```
┌─────────────────────────────────────────────────┐
│  ┌─────┐  Tên nhóm                    [⚙️]   │
│  │ 👥  │  5 thành viên                        │
│  │     │  [3] ← Unread badge                 │
│  └─────┘                                      │
└─────────────────────────────────────────────────┘
```

### Discover Groups (Right Column)
#### Header với Search
```
┌─────────────────────────────────────────────────┐
│  Khám phá nhóm                    [Search] [+] │
│  Tìm và tham gia các nhóm thú vị               │
├─────────────────────────────────────────────────┤
│  [Tất cả] [Đã tham gia] [Chưa tham gia]       │
└─────────────────────────────────────────────────┘
```

#### Group Cards Grid
```
┌─────────────────────────────────────────────────┐
│  ┌─────────────┐  ┌─────────────┐  ┌─────────┐ │
│  │    👥       │  │    👥       │  │   👥    │ │
│  │  Tên nhóm   │  │  Tên nhóm   │  │ Tên nhóm│ │
│  │  Mô tả...   │  │  Mô tả...   │  │ Mô tả...│ │
│  │  5 thành    │  │  3 thành    │  │ 0 thành │ │
│  │  [Tham gia] │  │  [Tham gia] │  │[Tham gia]│ │
│  └─────────────┘  └─────────────┘  └─────────┘ │
│                                                 │
│  ┌─────────────┐  ┌─────────────┐              │
│  │    👥       │  │    👥       │              │
│  │  Tên nhóm   │  │  Tên nhóm   │              │
│  │  Mô tả...   │  │  Mô tả...   │              │
│  │  2 thành    │  │  7 thành    │              │
│  │  [Tham gia] │  │  [Tham gia] │              │
│  └─────────────┘  └─────────────┘              │
└─────────────────────────────────────────────────┘
```

#### Empty State
```
┌─────────────────────────────────────────────────┐
│                                                 │
│              🌐                                │
│        Không có nhóm nào                       │
│     Hãy tạo nhóm đầu tiên của bạn              │
│                                                 │
└─────────────────────────────────────────────────┘
```

## 📝 Create Group Dialog

### Modal Structure
```
┌─────────────────────────────────────────────────┐
│  ┌─────────────────────────────────────────────┐ │
│  │  👥 Tạo nhóm mới                    [✕]   │ │
│  │     Tạo một nhóm chat mới để kết nối...    │ │
│  ├─────────────────────────────────────────────┤ │
│  │                                             │ │
│  │  ┌─────────────────────────────────────────┐ │ │
│  │  │  [Avatar Upload Area]                   │ │ │
│  │  │  Tải lên ảnh đại diện cho nhóm (tùy chọn)│ │ │
│  │  └─────────────────────────────────────────┘ │ │
│  │                                             │ │
│  │  Tên nhóm *                                │ │
│  │  [Input field] 0/50 ký tự                  │ │
│  │                                             │ │
│  │  Giới thiệu                                │ │
│  │  [Textarea] 0/200 ký tự                    │ │
│  │                                             │ │
│  │  ┌─────────────────────────────────────────┐ │ │
│  │  │  🔒 Cài đặt quyền riêng tư             │ │ │
│  │  │                                         │ │ │
│  │  │  ○ Nhóm riêng tư                        │ │ │
│  │  │    Chỉ mời mới vào được                 │ │ │
│  │  │                                         │ │ │
│  │  │  ○ Nhóm công khai                       │ │ │
│  │  │    Ai cũng có thể tham gia              │ │ │
│  │  │                                         │ │ │
│  │  │  ○ Cộng đồng                            │ │ │
│  │  │    Tập trung vào bài đăng               │ │ │
│  │  └─────────────────────────────────────────┘ │ │
│  │                                             │ │
│  │                    [Hủy] [Tạo nhóm]        │ │
│  └─────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────┘
```

## 🎨 Component Specifications

### Buttons
- **Primary Button**: 
  - Background: `from-[#ad46ff] to-[#1447e6]`
  - Text: white
  - Hover: `from-[#ad46ff]/90 to-[#1447e6]/90`
  - Shadow: `shadow-lg`, hover: `shadow-xl`

- **Secondary Button**:
  - Background: transparent
  - Border: `border-gray-200 dark:border-gray-700`
  - Hover: `bg-gray-50 dark:bg-gray-800`

- **Icon Button**:
  - Size: `h-8 w-8`, `h-10 w-10`, `h-14 w-14`
  - Rounded: `rounded-lg`, `rounded-xl`
  - Hover effects: `hover:scale-105`, `hover:shadow-md`

### Cards
- **Background**: `bg-white dark:bg-gray-950`
- **Border**: `border-gray-200 dark:border-gray-700`
- **Shadow**: `shadow-sm`, `shadow-md`, `shadow-lg`
- **Hover**: `hover:shadow-lg`, `hover:border-[#ad46ff]/20`

### Input Fields
- **Background**: `bg-gray-50 dark:bg-gray-900`
- **Border**: `border-gray-200 dark:border-gray-700`
- **Focus**: `focus:border-[#ad46ff] focus:ring-[#ad46ff]/20`
- **Placeholder**: `text-gray-400`

### Avatars
- **Size variants**: `h-8 w-8`, `h-12 w-12`, `h-16 w-16`, `h-24 w-24`
- **Fallback**: Gradient background với initials
- **Ring**: `ring-2 ring-gray-200 dark:ring-gray-700`

## 📱 Responsive Design

### Breakpoints
- **Mobile**: `< 768px` - Sidebar ẩn, content full-width
- **Tablet**: `768px - 1024px` - Sidebar thu gọn, content responsive
- **Desktop**: `> 1024px` - Sidebar cố định, content max-width

### Mobile Adaptations
- **Sidebar**: Sheet/drawer pattern
- **Grid**: Single column layout
- **Spacing**: Reduced padding/margins
- **Typography**: Smaller font sizes

## 🌙 Dark Mode Support

### Color Mapping
- **Background**: `bg-white` → `dark:bg-gray-950`
- **Surface**: `bg-gray-50` → `dark:bg-gray-900`
- **Border**: `border-gray-200` → `dark:border-gray-700`
- **Text**: `text-gray-900` → `dark:text-white`

### Dark Mode Specifics
- **Gradients**: Reduced opacity (`/20`, `/30`)
- **Shadows**: Darker shadows with opacity
- **Hover states**: Adjusted for dark backgrounds

## 🚀 Animation & Transitions

### Duration Classes
- **Fast**: `duration-150` (150ms)
- **Normal**: `duration-200` (200ms)
- **Slow**: `duration-300` (300ms)

### Transition Types
- **All**: `transition-all`
- **Colors**: `transition-colors`
- **Transform**: `transition-transform`
- **Shadow**: `transition-shadow`

### Hover Effects
- **Scale**: `hover:scale-105`, `hover:scale-110`
- **Shadow**: `hover:shadow-md`, `hover:shadow-lg`
- **Border**: `hover:border-[#ad46ff]/20`

## 📋 Implementation Checklist

### Core Components
- [ ] Sidebar Navigation
- [ ] Chat Interface
- [ ] Group Discovery
- [ ] Create Group Dialog
- [ ] User Search Popup
- [ ] Theme Toggle
- [ ] Notification System

### Layout Components
- [ ] Root Layout
- [ ] Customer Layout
- [ ] Chat Page Layout
- [ ] Discover Page Layout
- [ ] Profile Page Layout
- [ ] Posts Page Layout

### UI Components
- [ ] Buttons (Primary, Secondary, Icon)
- [ ] Input Fields
- [ ] Cards
- [ ] Avatars
- [ ] Badges
- [ ] Tabs
- [ ] Modals
- [ ] Tooltips

### Utilities
- [ ] Color system
- [ ] Typography scale
- [ ] Spacing system
- [ ] Animation classes
- [ ] Dark mode utilities

## 🔧 Technical Notes

### CSS Framework
- **Tailwind CSS** với custom color palette
- **CSS Variables** cho dynamic theming
- **CSS Modules** cho component-specific styles

### State Management
- **Zustand** cho global state
- **React Context** cho theme và auth
- **Local Storage** cho user preferences

### Performance
- **Lazy loading** cho routes
- **Image optimization** với Next.js Image
- **Code splitting** cho large components
- **Memoization** cho expensive operations

---

*Document này mô tả giao diện người dùng của FastBite Group. Sử dụng làm tài liệu tham khảo khi implement UI components và layouts.*
