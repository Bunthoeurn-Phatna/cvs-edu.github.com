READ me
<!doctype html>
<html lang="en">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cambodia Vision School Pro - Latest System</title>
  <script src="/_sdk/data_sdk.js"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      min-height: 100%;
      height: 100%;
      box-sizing: border-box;
    }
    
    html {
      height: 100%;
    }
    
    .app-wrapper {
      display: flex;
      height: 100%;
      width: 100%;
    }
    
    .sidebar {
      width: 290px;
      background: linear-gradient(180deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
      color: white;
      overflow-y: auto;
      flex-shrink: 0;
      box-shadow: 4px 0 30px rgba(0,0,0,0.4);
      position: relative;
    }
    
    .sidebar::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: url('data:image/svg+xml,<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg"><defs><pattern id="grid" width="20" height="20" patternUnits="userSpaceOnUse"><path d="M 20 0 L 0 0 0 20" fill="none" stroke="rgba(255,255,255,0.03)" stroke-width="1"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
      opacity: 0.5;
      pointer-events: none;
    }
    
    .logo-section {
      padding: 30px 20px;
      text-align: center;
      background: linear-gradient(135deg, rgba(102, 126, 234, 0.2) 0%, rgba(118, 75, 162, 0.2) 100%);
      border-bottom: 2px solid rgba(255,255,255,0.1);
      backdrop-filter: blur(10px);
      position: relative;
      z-index: 1;
    }
    
    .logo-icon {
      width: 80px;
      height: 80px;
      background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
      border-radius: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 40px;
      margin: 0 auto 15px;
      box-shadow: 0 10px 30px rgba(245, 87, 108, 0.5);
      animation: float 3s ease-in-out infinite;
    }
    
    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
    }
    
    .school-name {
      font-size: 20px;
      font-weight: 900;
      margin-bottom: 5px;
      color: #fff;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
      letter-spacing: 0.5px;
    }
    
    .school-tagline {
      font-size: 12px;
      color: #b8c5ff;
      font-weight: 600;
      letter-spacing: 1px;
    }
    
    .system-badge {
      display: inline-block;
      margin-top: 8px;
      padding: 4px 12px;
      background: linear-gradient(135deg, #ffd89b 0%, #19547b 100%);
      border-radius: 20px;
      font-size: 10px;
      font-weight: 700;
      letter-spacing: 0.5px;
      text-transform: uppercase;
      box-shadow: 0 4px 15px rgba(255, 216, 155, 0.3);
    }
    
    .nav-section {
      padding: 20px 12px;
      position: relative;
      z-index: 1;
    }
    
    .nav-section-title {
      font-size: 11px;
      font-weight: 800;
      text-transform: uppercase;
      color: #8b8ba7;
      margin: 20px 0 12px 10px;
      letter-spacing: 1.5px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    
    .nav-section-title::before {
      content: '';
      width: 3px;
      height: 12px;
      background: linear-gradient(180deg, #f093fb 0%, #f5576c 100%);
      border-radius: 2px;
    }
    
    .nav-menu {
      list-style: none;
    }
    
    .nav-item {
      margin-bottom: 4px;
    }
    
    .nav-link {
      display: flex;
      align-items: center;
      padding: 12px 14px;
      color: #b8c5ff;
      text-decoration: none;
      border-radius: 12px;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      cursor: pointer;
      font-size: 14px;
      font-weight: 600;
      position: relative;
      overflow: hidden;
    }
    
    .nav-link::before {
      content: '';
      position: absolute;
      left: 0;
      top: 0;
      bottom: 0;
      width: 0;
      background: linear-gradient(90deg, rgba(102, 126, 234, 0.3) 0%, transparent 100%);
      transition: width 0.3s ease;
    }
    
    .nav-link:hover::before {
      width: 100%;
    }
    
    .nav-link:hover {
      color: white;
      transform: translateX(5px);
      background: rgba(102, 126, 234, 0.15);
    }
    
    .nav-link.active {
      background: linear-gradient(135deg, rgba(102, 126, 234, 0.4) 0%, rgba(118, 75, 162, 0.4) 100%);
      color: white;
      font-weight: 700;
      box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
    }
    
    .nav-link.active::after {
      content: '';
      position: absolute;
      right: 10px;
      width: 6px;
      height: 6px;
      background: #4ade80;
      border-radius: 50%;
      box-shadow: 0 0 10px #4ade80;
    }
    
    .nav-icon {
      margin-right: 12px;
      font-size: 18px;
      min-width: 18px;
      filter: drop-shadow(0 2px 4px rgba(0,0,0,0.2));
    }
    
    .nav-badge {
      margin-left: auto;
      background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
      color: white;
      padding: 2px 8px;
      border-radius: 10px;
      font-size: 10px;
      font-weight: 700;
      box-shadow: 0 2px 8px rgba(245, 87, 108, 0.4);
    }
    
    .main-content {
      flex: 1;
      overflow-y: auto;
      background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
    }
    
    .top-bar {
      background: linear-gradient(135deg, #ffffff 0%, #f8f9ff 100%);
      padding: 20px 35px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.08);
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 3px solid #667eea;
      backdrop-filter: blur(10px);
    }
    
    .page-title-section {
      display: flex;
      align-items: center;
      gap: 15px;
    }
    
    .page-icon {
      width: 50px;
      height: 50px;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      border-radius: 14px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 24px;
      box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);
    }
    
    .page-title {
      font-size: 28px;
      font-weight: 900;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    
    .top-bar-actions {
      display: flex;
      align-items: center;
      gap: 15px;
    }
    
    .search-bar {
      position: relative;
    }
    
    .search-bar input {
      padding: 10px 40px 10px 16px;
      border: 2px solid #e5e7eb;
      border-radius: 12px;
      font-size: 14px;
      width: 250px;
      transition: all 0.3s;
    }
    
    .search-bar input:focus {
      outline: none;
      border-color: #667eea;
      box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
      width: 300px;
    }
    
    .search-icon {
      position: absolute;
      right: 12px;
      top: 50%;
      transform: translateY(-50%);
      font-size: 18px;
      color: #9ca3af;
    }
    
    .notification-btn {
      position: relative;
      width: 45px;
      height: 45px;
      background: linear-gradient(135deg, #ffeaa7 0%, #fdcb6e 100%);
      border: none;
      border-radius: 12px;
      font-size: 20px;
      cursor: pointer;
      box-shadow: 0 4px 15px rgba(253, 203, 110, 0.4);
      transition: all 0.3s;
    }
    
    .notification-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 25px rgba(253, 203, 110, 0.5);
    }
    
    .notification-badge {
      position: absolute;
      top: -5px;
      right: -5px;
      width: 20px;
      height: 20px;
      background: linear-gradient(135deg, #ff6b6b 0%, #ee5a6f 100%);
      color: white;
      border-radius: 50%;
      font-size: 11px;
      font-weight: 700;
      display: flex;
      align-items: center;
      justify-content: center;
      border: 2px solid white;
      box-shadow: 0 2px 8px rgba(238, 90, 111, 0.5);
    }
    
    .user-profile {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 8px 16px;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      border-radius: 25px;
      cursor: pointer;
      transition: all 0.3s;
      box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
    }
    
    .user-profile:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 25px rgba(102, 126, 234, 0.5);
    }
    
    .user-avatar {
      width: 35px;
      height: 35px;
      background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      border: 2px solid white;
    }
    
    .user-name {
      color: white;
      font-weight: 700;
      font-size: 14px;
    }
    
    .content-area {
      padding: 30px 35px;
    }
    
    .welcome-banner {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
      padding: 35px;
      border-radius: 20px;
      margin-bottom: 30px;
      box-shadow: 0 15px 40px rgba(102, 126, 234, 0.4);
      position: relative;
      overflow: hidden;
    }
    
    .welcome-banner::before {
      content: '';
      position: absolute;
      top: -50%;
      right: -10%;
      width: 400px;
      height: 400px;
      background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
      border-radius: 50%;
    }
    
    .welcome-content {
      position: relative;
      z-index: 1;
    }
    
    .welcome-text {
      font-size: 32px;
      font-weight: 900;
      margin-bottom: 8px;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
    }
    
    .welcome-subtext {
      font-size: 16px;
      opacity: 0.95;
      font-weight: 500;
    }
    
    .welcome-meta {
      margin-top: 20px;
      display: flex;
      gap: 25px;
      flex-wrap: wrap;
    }
    
    .meta-item {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      font-weight: 600;
    }
    
    .meta-icon {
      width: 35px;
      height: 35px;
      background: rgba(255,255,255,0.2);
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      backdrop-filter: blur(10px);
    }
    
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
      gap: 20px;
      margin-bottom: 30px;
    }
    
    .stat-card {
      background: white;
      padding: 25px;
      border-radius: 18px;
      box-shadow: 0 6px 20px rgba(0,0,0,0.08);
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      cursor: pointer;
      position: relative;
      overflow: hidden;
      border: 2px solid transparent;
    }
    
    .stat-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 4px;
      background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
    }
    
    .stat-card:hover {
      transform: translateY(-6px);
      box-shadow: 0 12px 35px rgba(0,0,0,0.12);
      border-color: #667eea;
    }
    
    .stat-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 15px;
    }
    
    .stat-icon {
      font-size: 40px;
      filter: drop-shadow(0 4px 8px rgba(0,0,0,0.15));
    }
    
    .stat-trend {
      padding: 4px 10px;
      background: linear-gradient(135deg, #d4fc79 0%, #96e6a1 100%);
      border-radius: 12px;
      font-size: 12px;
      font-weight: 700;
      color: #065f46;
      display: flex;
      align-items: center;
      gap: 4px;
    }
    
    .stat-label {
      color: #6b7280;
      font-size: 14px;
      font-weight: 700;
      margin-bottom: 10px;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }
    
    .stat-value {
      font-size: 36px;
      font-weight: 900;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      line-height: 1;
    }
    
    .stat-footer {
      margin-top: 12px;
      font-size: 12px;
      color: #9ca3af;
      font-weight: 600;
    }
    
    .btn {
      padding: 12px 24px;
      border: none;
      border-radius: 12px;
      font-weight: 700;
      cursor: pointer;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      font-size: 14px;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      font-family: inherit;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }
    
    .btn:hover:not(:disabled) {
      transform: translateY(-3px);
      box-shadow: 0 8px 25px rgba(0,0,0,0.15);
    }
    
    .btn:active:not(:disabled) {
      transform: translateY(-1px);
    }
    
    .btn:disabled {
      opacity: 0.6;
      cursor: not-allowed;
    }
    
    .btn-primary {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
    }
    
    .btn-secondary {
      background: linear-gradient(135deg, #e0e7ff 0%, #cfd9ff 100%);
      color: #4338ca;
    }
    
    .btn-danger {
      background: linear-gradient(135deg, #ff6b6b 0%, #ee5a6f 100%);
      color: white;
    }
    
    .btn-success {
      background: linear-gradient(135deg, #4ade80 0%, #22c55e 100%);
      color: white;
    }
    
    .btn-warning {
      background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
      color: white;
    }
    
    .btn-small {
      padding: 7px 14px;
      font-size: 12px;
      gap: 6px;
    }
    
    .data-section {
      background: white;
      border-radius: 20px;
      padding: 28px;
      box-shadow: 0 6px 25px rgba(0,0,0,0.08);
      margin-bottom: 25px;
      border: 1px solid #e5e7eb;
    }
    
    .section-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 25px;
      flex-wrap: wrap;
      gap: 15px;
      padding-bottom: 20px;
      border-bottom: 2px solid #f3f4f6;
    }
    
    .section-title {
      font-size: 22px;
      font-weight: 900;
      color: #1f2937;
      display: flex;
      align-items: center;
      gap: 12px;
    }
    
    .section-title-icon {
      width: 45px;
      height: 45px;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 22px;
      box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
    }
    
    .filter-bar {
      display: flex;
      gap: 12px;
      margin-bottom: 25px;
      flex-wrap: wrap;
      align-items: center;
    }
    
    .search-input {
      flex: 1;
      min-width: 250px;
      padding: 12px 18px;
      border: 2px solid #e5e7eb;
      border-radius: 12px;
      font-size: 14px;
      transition: all 0.3s;
      font-family: inherit;
    }
    
    .search-input:focus {
      outline: none;
      border-color: #667eea;
      box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
    }
    
    .filter-select {
      padding: 12px 18px;
      border: 2px solid #e5e7eb;
      border-radius: 12px;
      font-size: 14px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s;
      font-family: inherit;
    }
    
    .filter-select:focus {
      outline: none;
      border-color: #667eea;
    }
    
    .data-table {
      width: 100%;
      border-collapse: separate;
      border-spacing: 0;
      font-size: 14px;
    }
    
    .data-table th,
    .data-table td {
      padding: 16px;
      text-align: left;
    }
    
    .data-table thead {
      background: linear-gradient(135deg, #f9fafb 0%, #f3f4f6 100%);
    }
    
    .data-table th {
      font-weight: 800;
      color: #374151;
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.8px;
      border-bottom: 2px solid #e5e7eb;
    }
    
    .data-table th:first-child {
      border-top-left-radius: 12px;
    }
    
    .data-table th:last-child {
      border-top-right-radius: 12px;
    }
    
    .data-table td {
      color: #4b5563;
      font-weight: 600;
      border-bottom: 1px solid #f3f4f6;
    }
    
    .data-table tbody tr {
      transition: all 0.2s;
    }
    
    .data-table tbody tr:hover {
      background: linear-gradient(135deg, #faf5ff 0%, #f3e8ff 100%);
      transform: scale(1.01);
    }
    
    .data-table tbody tr:last-child td {
      border-bottom: none;
    }
    
    .badge {
      display: inline-block;
      padding: 6px 12px;
      border-radius: 20px;
      font-size: 11px;
      font-weight: 700;
      letter-spacing: 0.5px;
      text-transform: uppercase;
    }
    
    .badge-success {
      background: linear-gradient(135deg, #d4fc79 0%, #96e6a1 100%);
      color: #065f46;
    }
    
    .badge-danger {
      background: linear-gradient(135deg, #fecaca 0%, #fca5a5 100%);
      color: #991b1b;
    }
    
    .badge-warning {
      background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%);
      color: #92400e;
    }
    
    .badge-info {
      background: linear-gradient(135deg, #dbeafe 0%, #bfdbfe 100%);
      color: #1e40af;
    }
    
    .badge-primary {
      background: linear-gradient(135deg, #e0e7ff 0%, #c7d2fe 100%);
      color: #3730a3;
    }
    
    .empty-state {
      text-align: center;
      padding: 80px 20px;
    }
    
    .empty-icon {
      font-size: 90px;
      margin-bottom: 20px;
      opacity: 0.6;
      animation: float 3s ease-in-out infinite;
    }
    
    .empty-text {
      font-size: 22px;
      font-weight: 900;
      color: #1f2937;
      margin-bottom: 10px;
    }
    
    .empty-subtext {
      font-size: 15px;
      color: #6b7280;
      font-weight: 600;
      margin-bottom: 25px;
    }
    
    .modal-overlay {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: rgba(0,0,0,0.75);
      backdrop-filter: blur(8px);
      z-index: 1000;
      align-items: center;
      justify-content: center;
      padding: 20px;
      animation: fadeIn 0.3s ease;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    
    .modal-overlay.active {
      display: flex;
    }
    
    .modal {
      background: white;
      border-radius: 24px;
      padding: 35px;
      max-width: 650px;
      width: 100%;
      max-height: 85%;
      overflow-y: auto;
      box-shadow: 0 25px 80px rgba(0,0,0,0.4);
      animation: slideUp 0.3s ease;
    }
    
    @keyframes slideUp {
      from { 
        opacity: 0;
        transform: translateY(50px);
      }
      to { 
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    .modal-header {
      font-size: 26px;
      font-weight: 900;
      margin-bottom: 25px;
      color: #1f2937;
      display: flex;
      align-items: center;
      gap: 12px;
      padding-bottom: 20px;
      border-bottom: 2px solid #f3f4f6;
    }
    
    .modal-icon {
      width: 50px;
      height: 50px;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      border-radius: 14px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 24px;
      box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);
    }
    
    .form-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 18px;
    }
    
    .form-group {
      margin-bottom: 18px;
    }
    
    .form-group-full {
      grid-column: 1 / -1;
    }
    
    .form-label {
      display: block;
      margin-bottom: 8px;
      font-weight: 800;
      color: #374151;
      font-size: 13px;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }
    
    .form-input, .form-select, .form-textarea {
      width: 100%;
      padding: 12px 16px;
      border: 2px solid #e5e7eb;
      border-radius: 12px;
      font-size: 14px;
      outline: none;
      transition: all 0.3s;
      font-family: inherit;
      font-weight: 600;
    }
    
    .form-textarea {
      min-height: 120px;
      resize: vertical;
    }
    
    .form-input:focus, .form-select:focus, .form-textarea:focus {
      border-color: #667eea;
      box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
    }
    
    .form-actions {
      display: flex;
      gap: 12px;
      justify-content: flex-end;
      margin-top: 30px;
      padding-top: 25px;
      border-top: 2px solid #f3f4f6;
    }
    
    .toast {
      position: fixed;
      bottom: 30px;
      right: 30px;
      background: linear-gradient(135deg, #1f2937 0%, #374151 100%);
      color: white;
      padding: 18px 28px;
      border-radius: 14px;
      box-shadow: 0 10px 35px rgba(0,0,0,0.4);
      display: none;
      z-index: 2000;
      font-weight: 700;
      font-size: 14px;
      max-width: 450px;
      border: 2px solid rgba(255,255,255,0.1);
    }
    
    .toast.show {
      display: flex;
      align-items: center;
      gap: 12px;
      animation: slideInRight 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    @keyframes slideInRight {
      from {
        transform: translateX(500px);
        opacity: 0;
      }
      to {
        transform: translateX(0);
        opacity: 1;
      }
    }
    
    .toast.success {
      background: linear-gradient(135deg, #059669 0%, #10b981 100%);
      border-color: rgba(255,255,255,0.2);
    }
    
    .toast.error {
      background: linear-gradient(135deg, #dc2626 0%, #ef4444 100%);
      border-color: rgba(255,255,255,0.2);
    }
    
    .toast.warning {
      background: linear-gradient(135deg, #d97706 0%, #f59e0b 100%);
      border-color: rgba(255,255,255,0.2);
    }
    
    .toast-icon {
      font-size: 20px;
    }
    
    .login-screen {
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 100%;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      padding: 20px;
      width: 100%;
      position: relative;
      overflow: hidden;
    }
    
    .login-screen::before {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: radial-gradient(circle, rgba(255,255,255,0.1) 1px, transparent 1px);
      background-size: 50px 50px;
      animation: drift 20s linear infinite;
    }
    
    @keyframes drift {
      0% { transform: translate(0, 0); }
      100% { transform: translate(50px, 50px); }
    }
    
    .login-container {
      background: white;
      border-radius: 24px;
      padding: 50px;
      max-width: 450px;
      width: 100%;
      box-shadow: 0 30px 90px rgba(0,0,0,0.4);
      position: relative;
      z-index: 1;
      animation: fadeInUp 0.6s ease;
    }
    
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    .login-header {
      text-align: center;
      margin-bottom: 35px;
    }
    
    .login-logo {
      font-size: 70px;
      margin-bottom: 20px;
      animation: float 3s ease-in-out infinite;
    }
    
    .login-title {
      font-size: 28px;
      font-weight: 900;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin-bottom: 8px;
    }
    
    .login-subtitle {
      color: #6b7280;
      font-size: 14px;
      font-weight: 600;
    }
    
    .login-version {
      display: inline-block;
      margin-top: 10px;
      padding: 5px 15px;
      background: linear-gradient(135deg, #ffd89b 0%, #19547b 100%);
      color: white;
      border-radius: 20px;
      font-size: 12px;
      font-weight: 700;
      letter-spacing: 1px;
      text-transform: uppercase;
    }
    
    .login-hint {
      text-align: center;
      font-size: 12px;
      color: #6b7280;
      padding: 12px;
      background: linear-gradient(135deg, #f9fafb 0%, #f3f4f6 100%);
      border-radius: 12px;
      margin-top: 20px;
      font-weight: 700;
      border: 2px solid #e5e7eb;
    }
    
    .grid-2 {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 20px;
    }
    
    .card {
      background: white;
      border-radius: 18px;
      padding: 25px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.08);
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      cursor: pointer;
      border: 2px solid #f3f4f6;
    }
    
    .card:hover {
      box-shadow: 0 10px 35px rgba(0,0,0,0.12);
      transform: translateY(-5px);
      border-color: #667eea;
    }
    
    .card-header {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 15px;
    }
    
    .card-icon {
      width: 45px;
      height: 45px;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 22px;
      box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
    }
    
    .card-title {
      font-size: 18px;
      font-weight: 900;
      color: #1f2937;
      flex: 1;
    }
    
    .card-text {
      font-size: 14px;
      color: #6b7280;
      line-height: 1.7;
      font-weight: 600;
    }
    
    .card-text p {
      margin-bottom: 8px;
    }
    
    .quick-actions {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
      margin-top: 15px;
    }
    
    .quick-action-btn {
      flex: 1;
      min-width: 140px;
      padding: 14px;
      background: linear-gradient(135deg, #f3f4f6 0%, #e5e7eb 100%);
      border: 2px solid #d1d5db;
      border-radius: 12px;
      font-weight: 700;
      font-size: 13px;
      cursor: pointer;
      transition: all 0.3s;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
    }
    
    .quick-action-btn:hover {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
      border-color: #667eea;
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(102, 126, 234, 0.3);
    }
    
    .progress-bar {
      width: 100%;
      height: 8px;
      background: #e5e7eb;
      border-radius: 10px;
      overflow: hidden;
      margin-top: 12px;
    }
    
    .progress-fill {
      height: 100%;
      background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
      border-radius: 10px;
      transition: width 0.3s ease;
    }
    
    .action-buttons {
      display: flex;
      gap: 8px;
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="https://cdn.tailwindcss.com" type="text/javascript"></script>
 </head>
 <body>
  <div class="login-screen" id="loginScreen">
   <div class="login-container">
    <div class="login-header">
     <div class="login-logo">
      🎓
     </div>
     <h1 class="login-title" id="loginSchoolName">Cambodia Vision School Pro</h1>
     <p class="login-subtitle">Advanced Management System</p>
     <div class="login-version" id="loginVersion">
      Version 3.0 Pro
     </div>
    </div>
    <form id="loginForm">
     <div class="form-group"><label class="form-label" for="username">Username</label> <input type="text" id="username" class="form-input" required placeholder="Enter your username">
     </div>
     <div class="form-group"><label class="form-label" for="password">Password</label> <input type="password" id="password" class="form-input" required placeholder="Enter your password">
     </div><button type="submit" class="btn btn-primary" style="width: 100%; justify-content: center; margin-top: 10px;"> <span>🔐</span><span>Sign In</span> </button>
    </form>
    <div class="login-hint">
     🔑 Demo Credentials: admin / admin123
    </div>
   </div>
  </div>
  <div class="app-wrapper" id="appWrapper" style="display: none;">
   <aside class="sidebar">
    <div class="logo-section">
     <div class="logo-icon">
      🎓
     </div>
     <div class="school-name" id="schoolName">
      Cambodia Vision School Pro
     </div>
     <div class="school-tagline" id="schoolTagline">
      Excellence in Education
     </div>
     <div class="system-badge" id="systemVersion">
      v3.0 Pro
     </div>
    </div>
    <nav class="nav-section">
     <div class="nav-section-title">
      📊 Dashboard
     </div>
     <ul class="nav-menu">
      <li class="nav-item">
       <div class="nav-link active" data-page="dashboard"><span class="nav-icon">🏠</span> <span>Overview</span>
       </div></li>
     </ul>
     <div class="nav-section-title">
      🎓 Academic
     </div>
     <ul class="nav-menu">
      <li class="nav-item">
       <div class="nav-link" data-page="students"><span class="nav-icon">👨‍🎓</span> <span>Students</span> <span class="nav-badge" id="studentCount">0</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="teachers"><span class="nav-icon">👨‍🏫</span> <span>Teachers</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="classes"><span class="nav-icon">🏫</span> <span>Classes</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="attendance"><span class="nav-icon">📋</span> <span>Attendance</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="exams"><span class="nav-icon">📝</span> <span>Exams</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="assignments"><span class="nav-icon">📚</span> <span>Assignments</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="timetable"><span class="nav-icon">⏰</span> <span>Timetable</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="subjects"><span class="nav-icon">📖</span> <span>Subjects</span>
       </div></li>
     </ul>
     <div class="nav-section-title">
      💰 Finance
     </div>
     <ul class="nav-menu">
      <li class="nav-item">
       <div class="nav-link" data-page="fees"><span class="nav-icon">💰</span> <span>Fee Management</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="expenses"><span class="nav-icon">💸</span> <span>Expenses</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="salaries"><span class="nav-icon">💵</span> <span>Salaries</span>
       </div></li>
     </ul>
     <div class="nav-section-title">
      📢 Communication
     </div>
     <ul class="nav-menu">
      <li class="nav-item">
       <div class="nav-link" data-page="announcements"><span class="nav-icon">📢</span> <span>Announcements</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="events"><span class="nav-icon">📅</span> <span>Events</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="messages"><span class="nav-icon">💬</span> <span>Messages</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="parents"><span class="nav-icon">👪</span> <span>Parents</span>
       </div></li>
     </ul>
     <div class="nav-section-title">
      🏢 Resources
     </div>
     <ul class="nav-menu">
      <li class="nav-item">
       <div class="nav-link" data-page="library"><span class="nav-icon">📚</span> <span>Library</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="transport"><span class="nav-icon">🚌</span> <span>Transport</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="hostel"><span class="nav-icon">🏨</span> <span>Hostel</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="inventory"><span class="nav-icon">📦</span> <span>Inventory</span>
       </div></li>
     </ul>
     <div class="nav-section-title">
      👥 HR
     </div>
     <ul class="nav-menu">
      <li class="nav-item">
       <div class="nav-link" data-page="staff"><span class="nav-icon">👥</span> <span>Staff</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="departments"><span class="nav-icon">🏢</span> <span>Departments</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="leave"><span class="nav-icon">🗓️</span> <span>Leave</span>
       </div></li>
     </ul>
     <div class="nav-section-title">
      📊 Analytics
     </div>
     <ul class="nav-menu">
      <li class="nav-item">
       <div class="nav-link" data-page="reports"><span class="nav-icon">📊</span> <span>Reports</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="analytics"><span class="nav-icon">📈</span> <span>Analytics</span>
       </div></li>
     </ul>
     <div class="nav-section-title">
      ⚙️ System
     </div>
     <ul class="nav-menu">
      <li class="nav-item">
       <div class="nav-link" data-page="complaints"><span class="nav-icon">📝</span> <span>Complaints</span>
       </div></li>
      <li class="nav-item">
       <div class="nav-link" data-page="settings"><span class="nav-icon">⚙️</span> <span>Settings</span>
       </div></li>
     </ul>
    </nav>
   </aside>
   <main class="main-content">
    <div class="top-bar">
     <div class="page-title-section">
      <div class="page-icon" id="pageIcon">
       🏠
      </div>
      <h1 class="page-title" id="pageTitle">Dashboard Overview</h1>
     </div>
     <div class="top-bar-actions">
      <div class="search-bar"><input type="text" placeholder="Search anything..." id="globalSearch"> <span class="search-icon">🔍</span>
      </div><button class="notification-btn" onclick="showToast('No new notifications', 'success')"> 🔔 <span class="notification-badge">3</span> </button> <select class="filter-select" id="languageSelector" onchange="changeLanguage(this.value)" style="padding: 8px 12px; margin-right: 10px; font-size: 13px; font-weight: 700;"> <option value="en">🇬🇧 English</option> <option value="km">🇰🇭 ភាសាខ្មែរ (Khmer)</option> <option value="zh">🇨🇳 中文 (Chinese)</option> <option value="vi">🇻🇳 Tiếng Việt (Vietnamese)</option> <option value="th">🇹🇭 ไทย (Thai)</option> <option value="fr">🇫🇷 Français (French)</option> <option value="es">🇪🇸 Español (Spanish)</option> </select>
      <div class="user-profile">
       <div class="user-avatar">
        👤
       </div><span class="user-name">Administrator</span>
      </div>
     </div>
    </div>
    <div class="content-area" id="contentArea"></div>
   </main>
  </div>
  <div id="modalContainer"></div>
  <div class="toast" id="toast"></div>
  <script>
    const defaultConfig = {
      school_name: "Cambodia Vision School Pro",
      school_tagline: "Excellence in Education",
      welcome_message: "Welcome to Cambodia Vision School Pro",
      system_version: "v3.0 Pro"
    };
    
    let allData = [];
    let currentPage = 'dashboard';
    let searchQuery = '';
    let currentLanguage = 'en';
    
    const translations = {
      en: {
        dashboard: 'Dashboard Overview',
        students: 'Student Management',
        teachers: 'Teacher Management',
        classes: 'Class Management',
        attendance: 'Attendance Tracking',
        exams: 'Exams & Results',
        assignments: 'Assignment Management',
        timetable: 'Class Timetable',
        subjects: 'Subject Management',
        fees: 'Fee Management',
        expenses: 'Expense Tracking',
        salaries: 'Salary Management',
        announcements: 'Announcements',
        events: 'Events Calendar',
        messages: 'Messaging Center',
        parents: 'Parent Portal',
        library: 'Library Management',
        transport: 'Transport Management',
        hostel: 'Hostel Management',
        inventory: 'Inventory System',
        staff: 'Staff Management',
        departments: 'Department Structure',
        leave: 'Leave Management',
        reports: 'Reports Center',
        analytics: 'Analytics Dashboard',
        complaints: 'Complaints & Feedback',
        settings: 'System Settings',
        addStudent: 'Add Student',
        addTeacher: 'Add Teacher',
        welcomeMessage: 'Welcome to Cambodia Vision School Pro'
      },
      km: {
        dashboard: 'ផ្ទាំងគ្រប់គ្រង',
        students: 'គ្រប់គ្រងសិស្ស',
        teachers: 'គ្រប់គ្រងគ្រូបង្រៀន',
        classes: 'គ្រប់គ្រងថ្នាក់',
        attendance: 'តាមដានវត្តមាន',
        exams: 'ប្រឡង និងលទ្ធផល',
        assignments: 'គ្រប់គ្រងកិច្ចការ',
        timetable: 'កាលវិភាគថ្នាក់',
        subjects: 'គ្រប់គ្រងមុខវិជ្ជា',
        fees: 'គ្រប់គ្រងថ្លៃសិក្សា',
        expenses: 'តាមដានចំណាយ',
        salaries: 'គ្រប់គ្រងប្រាក់ខែ',
        announcements: 'សេចក្តីប្រកាស',
        events: 'ប្រតិទិនព្រឹត្តិការណ៍',
        messages: 'មជ្ឈមណ្ឌលសារ',
        parents: 'ច្រកភ្ជាប់ឪពុកម្តាយ',
        library: 'គ្រប់គ្រងបណ្ណាល័យ',
        transport: 'គ្រប់គ្រងការដឹកជញ្ជូន',
        hostel: 'គ្រប់គ្រងអន្តេវាសិកដ្ឋាន',
        inventory: 'ប្រព័ន្ធសារពើភ័ណ្ឌ',
        staff: 'គ្រប់គ្រងបុគ្គលិក',
        departments: 'រចនាសម្ព័ន្ធផ្នែក',
        leave: 'គ្រប់គ្រងច្បាប់',
        reports: 'មជ្ឈមណ្ឌលរបាយការណ៍',
        analytics: 'ផ្ទាំងវិភាគ',
        complaints: 'បណ្តឹងតវ៉ា និងមតិត្រឡប់',
        settings: 'ការកំណត់ប្រព័ន្ធ',
        addStudent: 'បន្ថែមសិស្ស',
        addTeacher: 'បន្ថែមគ្រូបង្រៀន',
        welcomeMessage: 'សូមស្វាគមន៍មកកាន់សាលាវិស័យកម្ពុជា Pro'
      },
      zh: {
        dashboard: '仪表板概览',
        students: '学生管理',
        teachers: '教师管理',
        classes: '班级管理',
        attendance: '出勤跟踪',
        exams: '考试与成绩',
        assignments: '作业管理',
        timetable: '课程表',
        subjects: '科目管理',
        fees: '费用管理',
        expenses: '费用跟踪',
        salaries: '工资管理',
        announcements: '公告',
        events: '活动日历',
        messages: '消息中心',
        parents: '家长门户',
        library: '图书馆管理',
        transport: '交通管理',
        hostel: '宿舍管理',
        inventory: '库存系统',
        staff: '员工管理',
        departments: '部门结构',
        leave: '请假管理',
        reports: '报告中心',
        analytics: '分析仪表板',
        complaints: '投诉与反馈',
        settings: '系统设置',
        addStudent: '添加学生',
        addTeacher: '添加教师',
        welcomeMessage: '欢迎来到柬埔寨愿景学校专业版'
      },
      vi: {
        dashboard: 'Tổng quan Bảng điều khiển',
        students: 'Quản lý Học sinh',
        teachers: 'Quản lý Giáo viên',
        classes: 'Quản lý Lớp học',
        attendance: 'Theo dõi Điểm danh',
        exams: 'Kỳ thi & Kết quả',
        assignments: 'Quản lý Bài tập',
        timetable: 'Thời khóa biểu',
        subjects: 'Quản lý Môn học',
        fees: 'Quản lý Học phí',
        expenses: 'Theo dõi Chi phí',
        salaries: 'Quản lý Lương',
        announcements: 'Thông báo',
        events: 'Lịch Sự kiện',
        messages: 'Trung tâm Tin nhắn',
        parents: 'Cổng Phụ huynh',
        library: 'Quản lý Thư viện',
        transport: 'Quản lý Vận chuyển',
        hostel: 'Quản lý Ký túc xá',
        inventory: 'Hệ thống Kho',
        staff: 'Quản lý Nhân viên',
        departments: 'Cấu trúc Phòng ban',
        leave: 'Quản lý Nghỉ phép',
        reports: 'Trung tâm Báo cáo',
        analytics: 'Bảng Phân tích',
        complaints: 'Khiếu nại & Phản hồi',
        settings: 'Cài đặt Hệ thống',
        addStudent: 'Thêm Học sinh',
        addTeacher: 'Thêm Giáo viên',
        welcomeMessage: 'Chào mừng đến với Trường Vision Cambodia Pro'
      },
      th: {
        dashboard: 'ภาพรวมแดชบอร์ด',
        students: 'จัดการนักเรียน',
        teachers: 'จัดการครู',
        classes: 'จัดการชั้นเรียน',
        attendance: 'ติดตามการเข้าเรียน',
        exams: 'การสอบและผลลัพธ์',
        assignments: 'จัดการการบ้าน',
        timetable: 'ตารางเรียน',
        subjects: 'จัดการวิชา',
        fees: 'จัดการค่าธรรมเนียม',
        expenses: 'ติดตามค่าใช้จ่าย',
        salaries: 'จัดการเงินเดือน',
        announcements: 'ประกาศ',
        events: 'ปฏิทินกิจกรรม',
        messages: 'ศูนย์ข้อความ',
        parents: 'พอร์ทัลผู้ปกครอง',
        library: 'จัดการห้องสมุด',
        transport: 'จัดการการขนส่ง',
        hostel: 'จัดการหอพัก',
        inventory: 'ระบบสินค้าคงคลัง',
        staff: 'จัดการพนักงาน',
        departments: 'โครงสร้างแผนก',
        leave: 'จัดการการลา',
        reports: 'ศูนย์รายงาน',
        analytics: 'แดชบอร์ดการวิเคราะห์',
        complaints: 'ข้อร้องเรียนและคำติชม',
        settings: 'การตั้งค่าระบบ',
        addStudent: 'เพิ่มนักเรียน',
        addTeacher: 'เพิ่มครู',
        welcomeMessage: 'ยินดีต้อนรับสู่โรงเรียน Cambodia Vision Pro'
      },
      fr: {
        dashboard: 'Aperçu du Tableau de bord',
        students: 'Gestion des Étudiants',
        teachers: 'Gestion des Enseignants',
        classes: 'Gestion des Classes',
        attendance: 'Suivi de la Présence',
        exams: 'Examens et Résultats',
        assignments: 'Gestion des Devoirs',
        timetable: 'Emploi du temps',
        subjects: 'Gestion des Matières',
        fees: 'Gestion des Frais',
        expenses: 'Suivi des Dépenses',
        salaries: 'Gestion des Salaires',
        announcements: 'Annonces',
        events: 'Calendrier des Événements',
        messages: 'Centre de Messages',
        parents: 'Portail Parents',
        library: 'Gestion de la Bibliothèque',
        transport: 'Gestion du Transport',
        hostel: 'Gestion de l\'Internat',
        inventory: 'Système d\'Inventaire',
        staff: 'Gestion du Personnel',
        departments: 'Structure des Départements',
        leave: 'Gestion des Congés',
        reports: 'Centre de Rapports',
        analytics: 'Tableau de bord Analytique',
        complaints: 'Plaintes et Commentaires',
        settings: 'Paramètres du Système',
        addStudent: 'Ajouter un Étudiant',
        addTeacher: 'Ajouter un Enseignant',
        welcomeMessage: 'Bienvenue à Cambodia Vision School Pro'
      },
      es: {
        dashboard: 'Panel de Control General',
        students: 'Gestión de Estudiantes',
        teachers: 'Gestión de Profesores',
        classes: 'Gestión de Clases',
        attendance: 'Seguimiento de Asistencia',
        exams: 'Exámenes y Resultados',
        assignments: 'Gestión de Tareas',
        timetable: 'Horario de Clases',
        subjects: 'Gestión de Asignaturas',
        fees: 'Gestión de Cuotas',
        expenses: 'Seguimiento de Gastos',
        salaries: 'Gestión de Salarios',
        announcements: 'Anuncios',
        events: 'Calendario de Eventos',
        messages: 'Centro de Mensajes',
        parents: 'Portal de Padres',
        library: 'Gestión de Biblioteca',
        transport: 'Gestión de Transporte',
        hostel: 'Gestión de Residencia',
        inventory: 'Sistema de Inventario',
        staff: 'Gestión de Personal',
        departments: 'Estructura de Departamentos',
        leave: 'Gestión de Permisos',
        reports: 'Centro de Informes',
        analytics: 'Panel de Análisis',
        complaints: 'Quejas y Comentarios',
        settings: 'Configuración del Sistema',
        addStudent: 'Agregar Estudiante',
        addTeacher: 'Agregar Profesor',
        welcomeMessage: 'Bienvenido a Cambodia Vision School Pro'
      }
    };
    
    function changeLanguage(lang) {
      currentLanguage = lang;
      document.getElementById('pageTitle').textContent = translations[lang][currentPage] || getPageInfo(currentPage).title;
      renderCurrentPage();
      showToast(`✅ Language changed to ${lang === 'km' ? 'ភាសាខ្មែរ' : lang === 'zh' ? '中文' : lang === 'vi' ? 'Tiếng Việt' : lang === 'th' ? 'ไทย' : lang === 'fr' ? 'Français' : lang === 'es' ? 'Español' : 'English'}`, 'success');
    }
    
    const dataHandler = {
      onDataChanged(data) {
        allData = data;
        updateStats();
        renderCurrentPage();
      }
    };
    
    async function initApp() {
      const result = await window.dataSdk.init(dataHandler);
      if (!result.isOk) {
        showToast('Failed to initialize application', 'error');
        return;
      }
      
      if (window.elementSdk) {
        window.elementSdk.init({
          defaultConfig,
          onConfigChange: async (config) => {
            document.getElementById('schoolName').textContent = config.school_name || defaultConfig.school_name;
            document.getElementById('loginSchoolName').textContent = config.school_name || defaultConfig.school_name;
            document.getElementById('schoolTagline').textContent = config.school_tagline || defaultConfig.school_tagline;
            document.getElementById('systemVersion').textContent = config.system_version || defaultConfig.system_version;
            document.getElementById('loginVersion').textContent = config.system_version || defaultConfig.system_version;
            
            const welcomeText = document.querySelector('.welcome-text');
            if (welcomeText) {
              welcomeText.textContent = config.welcome_message || defaultConfig.welcome_message;
            }
          },
          mapToCapabilities: (config) => ({
            recolorables: [],
            borderables: [],
            fontEditable: undefined,
            fontSizeable: undefined
          }),
          mapToEditPanelValues: (config) => new Map([
            ['school_name', config.school_name || defaultConfig.school_name],
            ['school_tagline', config.school_tagline || defaultConfig.school_tagline],
            ['welcome_message', config.welcome_message || defaultConfig.welcome_message],
            ['system_version', config.system_version || defaultConfig.system_version]
          ])
        });
      }
      
      setupNavigation();
      setupLogin();
      setupGlobalSearch();
    }
    
    function setupLogin() {
      document.getElementById('loginForm').onsubmit = function(e) {
        e.preventDefault();
        const username = document.getElementById('username').value;
        const password = document.getElementById('password').value;
        
        if (username === 'admin' && password === 'admin123') {
          document.getElementById('loginScreen').style.display = 'none';
          document.getElementById('appWrapper').style.display = 'flex';
          showToast('🎉 Login successful! Welcome back, Administrator', 'success');
          renderDashboard();
        } else {
          showToast('❌ Invalid credentials. Please try again.', 'error');
        }
      };
    }
    
    function setupNavigation() {
      document.querySelectorAll('.nav-link').forEach(link => {
        link.onclick = function() {
          const page = this.getAttribute('data-page');
          switchPage(page);
        };
      });
    }
    
    function setupGlobalSearch() {
      const searchInput = document.getElementById('globalSearch');
      searchInput.oninput = function(e) {
        searchQuery = e.target.value.toLowerCase();
        renderCurrentPage();
      };
    }
    
    function switchPage(page) {
      currentPage = page;
      searchQuery = '';
      document.getElementById('globalSearch').value = '';
      
      document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
      const activeLink = document.querySelector(`[data-page="${page}"]`);
      if (activeLink) activeLink.classList.add('active');
      
      const pageInfo = getPageInfo(page);
      document.getElementById('pageTitle').textContent = translations[currentLanguage][page] || pageInfo.title;
      document.getElementById('pageIcon').textContent = pageInfo.icon;
      
      renderCurrentPage();
    }
    
    function getPageInfo(page) {
      const pages = {
        dashboard: { title: 'Dashboard Overview', icon: '🏠' },
        students: { title: 'Student Management', icon: '👨‍🎓' },
        teachers: { title: 'Teacher Management', icon: '👨‍🏫' },
        classes: { title: 'Class Management', icon: '🏫' },
        attendance: { title: 'Attendance Tracking', icon: '📋' },
        exams: { title: 'Exams & Results', icon: '📝' },
        assignments: { title: 'Assignment Management', icon: '📚' },
        timetable: { title: 'Class Timetable', icon: '⏰' },
        subjects: { title: 'Subject Management', icon: '📖' },
        fees: { title: 'Fee Management', icon: '💰' },
        expenses: { title: 'Expense Tracking', icon: '💸' },
        salaries: { title: 'Salary Management', icon: '💵' },
        announcements: { title: 'Announcements', icon: '📢' },
        events: { title: 'Events Calendar', icon: '📅' },
        messages: { title: 'Messaging Center', icon: '💬' },
        parents: { title: 'Parent Portal', icon: '����' },
        library: { title: 'Library Management', icon: '📚' },
        transport: { title: 'Transport Management', icon: '🚌' },
        hostel: { title: 'Hostel Management', icon: '🏨' },
        inventory: { title: 'Inventory System', icon: '📦' },
        staff: { title: 'Staff Management', icon: '👥' },
        departments: { title: 'Department Structure', icon: '🏢' },
        leave: { title: 'Leave Management', icon: '🗓️' },
        reports: { title: 'Reports Center', icon: '📊' },
        analytics: { title: 'Analytics Dashboard', icon: '📈' },
        complaints: { title: 'Complaints & Feedback', icon: '📝' },
        settings: { title: 'System Settings', icon: '⚙️' }
      };
      return pages[page] || { title: 'School Management', icon: '🏫' };
    }
    
    function updateStats() {
      const students = allData.filter(d => d.type === 'student');
      const studentCountEl = document.getElementById('studentCount');
      if (studentCountEl) {
        studentCountEl.textContent = students.length;
      }
    }
    
    function renderCurrentPage() {
      const pageRenderers = {
        dashboard: renderDashboard,
        students: renderStudents,
        teachers: renderTeachers,
        classes: renderClasses,
        attendance: renderAttendance,
        exams: renderExams,
        assignments: renderAssignments,
        timetable: renderTimetable,
        subjects: renderSubjects,
        fees: renderFees,
        expenses: renderExpenses,
        salaries: renderSalaries,
        announcements: renderAnnouncements,
        events: renderEvents,
        messages: renderMessages,
        parents: renderParents,
        library: renderLibrary,
        transport: renderTransport,
        hostel: renderHostel,
        inventory: renderInventory,
        staff: renderStaff,
        departments: renderDepartments,
        leave: renderLeave,
        reports: renderReports,
        analytics: renderAnalytics,
        complaints: renderComplaints,
        settings: renderSettings
      };
      
      const renderer = pageRenderers[currentPage];
      if (renderer) renderer();
    }
    
    function filterData(data) {
      if (!searchQuery) return data;
      
      return data.filter(item => {
        return Object.values(item).some(value => {
          if (value === null || value === undefined) return false;
          return String(value).toLowerCase().includes(searchQuery);
        });
      });
    }
    
    function renderDashboard() {
      const students = allData.filter(d => d.type === 'student');
      const teachers = allData.filter(d => d.type === 'teacher');
      const classes = allData.filter(d => d.type === 'class');
      const events = allData.filter(d => d.type === 'event');
      const announcements = allData.filter(d => d.type === 'announcement');
      const fees = allData.filter(d => d.type === 'fee');
      const paidFees = fees.filter(f => f.paid);
      const pendingFees = fees.filter(f => !f.paid);
      const totalRevenue = paidFees.reduce((sum, f) => sum + (parseFloat(f.amount) || 0), 0);
      const attendance = allData.filter(d => d.type === 'attendance');
      const presentToday = attendance.filter(a => a.present).length;
      const attendanceRate = attendance.length > 0 ? Math.round((presentToday / attendance.length) * 100) : 0;
      
      document.getElementById('contentArea').innerHTML = `
        <div class="welcome-banner">
          <div class="welcome-content">
            <div class="welcome-text">Welcome to Cambodia Vision School Pro</div>
            <div class="welcome-subtext">Your comprehensive school management solution - Latest Version</div>
            
            <div class="welcome-meta">
              <div class="meta-item">
                <div class="meta-icon">📅</div>
                <div>
                  <div style="font-size: 11px; opacity: 0.8;">Today's Date</div>
                  <div style="font-weight: 800;">${new Date().toLocaleDateString('en-US', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' })}</div>
                </div>
              </div>
              
              <div class="meta-item">
                <div class="meta-icon">🎓</div>
                <div>
                  <div style="font-size: 11px; opacity: 0.8;">Academic Year</div>
                  <div style="font-weight: 800;">2024-2025</div>
                </div>
              </div>
              
              <div class="meta-item">
                <div class="meta-icon">⭐</div>
                <div>
                  <div style="font-size: 11px; opacity: 0.8;">System Status</div>
                  <div style="font-weight: 800;">All Systems Operational</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <div class="stats-grid">
          <div class="stat-card" onclick="switchPage('students')">
            <div class="stat-header">
              <div class="stat-icon">👨‍🎓</div>
              <div class="stat-trend">↗ Active</div>
            </div>
            <div class="stat-label">Total Students</div>
            <div class="stat-value">${students.length}</div>
            <div class="stat-footer">All enrolled students</div>
          </div>
          
          <div class="stat-card" onclick="switchPage('teachers')">
            <div class="stat-header">
              <div class="stat-icon">👨‍🏫</div>
              <div class="stat-trend">����� Online</div>
            </div>
            <div class="stat-label">Teaching Staff</div>
            <div class="stat-value">${teachers.length}</div>
            <div class="stat-footer">Active teachers</div>
          </div>
          
          <div class="stat-card" onclick="switchPage('classes')">
            <div class="stat-header">
              <div class="stat-icon">🏫</div>
              <div class="stat-trend">📚 Active</div>
            </div>
            <div class="stat-label">Classes</div>
            <div class="stat-value">${classes.length}</div>
            <div class="stat-footer">Running classes</div>
          </div>
          
          <div class="stat-card" onclick="switchPage('fees')">
            <div class="stat-header">
              <div class="stat-icon">💰</div>
              <div class="stat-trend">💵 ${Math.round((paidFees.length/(fees.length || 1))*100)}%</div>
            </div>
            <div class="stat-label">Revenue</div>
            <div class="stat-value">$${totalRevenue.toLocaleString()}</div>
            <div class="stat-footer">${pendingFees.length} pending fees</div>
          </div>
          
          <div class="stat-card" onclick="switchPage('attendance')">
            <div class="stat-header">
              <div class="stat-icon">📋</div>
              <div class="stat-trend">✓ ${attendanceRate}%</div>
            </div>
            <div class="stat-label">Attendance</div>
            <div class="stat-value">${presentToday}/${attendance.length}</div>
            <div class="stat-footer">Present today</div>
          </div>
          
          <div class="stat-card" onclick="switchPage('events')">
            <div class="stat-header">
              <div class="stat-icon">������</div>
              <div class="stat-trend">📌 Upcoming</div>
            </div>
            <div class="stat-label">Events</div>
            <div class="stat-value">${events.length}</div>
            <div class="stat-footer">Scheduled events</div>
          </div>
          
          <div class="stat-card" onclick="switchPage('announcements')">
            <div class="stat-header">
              <div class="stat-icon">📢</div>
              <div class="stat-trend">🆕 New</div>
            </div>
            <div class="stat-label">Announcements</div>
            <div class="stat-value">${announcements.length}</div>
            <div class="stat-footer">Active announcements</div>
          </div>
          
          <div class="stat-card" onclick="switchPage('analytics')">
            <div class="stat-header">
              <div class="stat-icon">📈</div>
              <div class="stat-trend">📊 Live</div>
            </div>
            <div class="stat-label">Analytics</div>
            <div class="stat-value">${allData.length}</div>
            <div class="stat-footer">Total records</div>
          </div>
        </div>
        
        <div class="grid-2">
          <div class="card">
            <div class="card-header">
              <div class="card-icon">🎯</div>
              <div class="card-title">Quick Actions</div>
            </div>
            <div class="card-text">
              <p>Perform common tasks quickly and efficiently</p>
            </div>
            <div class="quick-actions">
              <button class="quick-action-btn" onclick="switchPage('students')">
                <span>➕</span><span>Add Student</span>
              </button>
              <button class="quick-action-btn" onclick="switchPage('attendance')">
                <span>✓</span><span>Mark Attendance</span>
              </button>
              <button class="quick-action-btn" onclick="switchPage('fees')">
                <span>💰</span><span>Collect Fee</span>
              </button>
              <button class="quick-action-btn" onclick="switchPage('announcements')">
                <span>📢</span><span>Announce</span>
              </button>
            </div>
          </div>
          
          <div class="card">
            <div class="card-header">
              <div class="card-icon">📊</div>
              <div class="card-title">System Overview</div>
            </div>
            <div class="card-text">
              <p><strong>�� Total Modules:</strong> 30 Complete Modules</p>
              <p><strong>💾 Data Storage:</strong> Canva Sheet Integration</p>
              <p><strong>🔒 Security:</strong> Role-based Access</p>
              <p><strong>⚡ Performance:</strong> Real-time Updates</p>
              <p><strong>📱 Platform:</strong> Fully Responsive</p>
            </div>
          </div>
          
          <div class="card">
            <div class="card-header">
              <div class="card-icon">🏆</div>
              <div class="card-title">Latest Features</div>
            </div>
            <div class="card-text">
              <p>✨ <strong>Enhanced UI/UX</strong> - Modern gradient design</p>
              <p>🚀 <strong>Performance</strong> - Optimized data handling</p>
              <p>📊 <strong>Advanced Analytics</strong> - Real-time insights</p>
              <p>🔔 <strong>Notifications</strong> - Smart alert system</p>
              <p>🎨 <strong>Customizable</strong> - Editable branding</p>
            </div>
          </div>
          
          <div class="card">
            <div class="card-header">
              <div class="card-icon">💡</div>
              <div class="card-title">Tips & Tricks</div>
            </div>
            <div class="card-text">
              <p>🔍 Use global search to find anything quickly</p>
              <p>📈 Check analytics for detailed insights</p>
              <p>⚡ All data saves automatically to your sheet</p>
              <p>�� Click stat cards for quick navigation</p>
              <p>✏️ Edit school branding in settings</p>
            </div>
          </div>
        </div>
      `;
    }
    
    function renderStudents() {
      const students = filterData(allData.filter(d => d.type === 'student'));
      renderDataList('student', students, [
        { key: 'student_id', label: 'Student ID' },
        { key: 'first_name', label: 'First Name' },
        { key: 'last_name', label: 'Last Name' },
        { key: 'gender', label: 'Gender' },
        { key: 'dob', label: 'Date of Birth' },
        { key: 'admission_date', label: 'Enrolled Date' },
        { key: 'grade', label: 'Grade' },
        { key: 'class_field', label: 'Section' },
        { key: 'shift', label: 'Session' },
        { key: 'village', label: 'Village' },
        { key: 'commune', label: 'Commune' },
        { key: 'district', label: 'District' },
        { key: 'province', label: 'Province' },
        { key: 'status', label: 'Status', badge: true }
      ], getStudentForm, '👨‍🎓', 'No students found', 'Add your first student to get started');
    }
    
    function renderTeachers() {
      const teachers = filterData(allData.filter(d => d.type === 'teacher'));
      renderDataList('teacher', teachers, [
        { key: 'teacher_name', label: 'Name' },
        { key: 'subject', label: 'Subject' },
        { key: 'email', label: 'Email' },
        { key: 'phone', label: 'Phone' },
        { key: 'qualification', label: 'Qualification' },
        { key: 'experience', label: 'Experience (yrs)' }
      ], getTeacherForm, '👨‍🏫', 'No teachers found', 'Add teaching staff members');
    }
    
    function renderClasses() {
      const classes = filterData(allData.filter(d => d.type === 'class'));
      renderDataList('class', classes, [
        { key: 'class_name', label: 'Class Name' },
        { key: 'grade', label: 'Grade' },
        { key: 'room_number', label: 'Room' },
        { key: 'capacity', label: 'Capacity' },
        { key: 'teacher_name', label: 'Class Teacher' }
      ], getClassForm, '🏫', 'No classes found', 'Create your first class');
    }
    
    function renderAttendance() {
      const attendance = filterData(allData.filter(d => d.type === 'attendance'));
      renderDataList('attendance', attendance, [
        { key: 'attendance_date', label: 'Date' },
        { key: 'student_id', label: 'Student ID' },
        { key: 'first_name', label: 'Student Name' },
        { key: 'class', label: 'Class' },
        { key: 'present', label: 'Status', badge: true }
      ], getAttendanceForm, '📋', 'No attendance records', 'Mark attendance for today');
    }
    
    function renderExams() {
      const exams = filterData(allData.filter(d => d.type === 'exam'));
      renderDataList('exam', exams, [
        { key: 'exam_name', label: 'Exam' },
        { key: 'student_id', label: 'Student ID' },
        { key: 'subject', label: 'Subject' },
        { key: 'score', label: 'Score' },
        { key: 'total_marks', label: 'Total' },
        { key: 'grade', label: 'Grade' }
      ], getExamForm, '📝', 'No exam results', 'Add exam results');
    }
    
    function renderAssignments() {
      const assignments = filterData(allData.filter(d => d.type === 'assignment'));
      renderDataList('assignment', assignments, [
        { key: 'assignment_title', label: 'Title' },
        { key: 'subject', label: 'Subject' },
        { key: 'class', label: 'Class' },
        { key: 'due_date', label: 'Due Date' },
        { key: 'submitted', label: 'Submitted', badge: true }
      ], getAssignmentForm, '📚', 'No assignments', 'Create new assignment');
    }
    
    function renderTimetable() {
      const timetable = filterData(allData.filter(d => d.type === 'timetable'));
      
      document.getElementById('contentArea').innerHTML = `
        <div class="data-section">
          <div class="section-header">
            <h2 class="section-title">
              <div class="section-title-icon">⏰</div>
              <span>Class Timetable</span>
            </h2>
            <button class="btn btn-primary" onclick="openModal('timetable')">
              <span>➕</span><span>Add Schedule</span>
            </button>
          </div>
          
          ${timetable.length === 0 ? `
            <div class="empty-state">
              <div class="empty-icon">⏰</div>
              <div class="empty-text">No timetable entries</div>
              <div class="empty-subtext">Create weekly class schedule</div>
            </div>
          ` : `
            <div class="grid-2">
              ${timetable.map(t => `
                <div class="card">
                  <div class="card-header">
                    <div class="card-icon">📚</div>
                    <div class="card-title">${t.subject || 'Subject'}</div>
                  </div>
                  <div class="card-text">
                    <p><strong>Day:</strong> ${t.day_of_week || 'N/A'}</p>
                    <p><strong>Time:</strong> ${t.start_time || 'N/A'} - ${t.end_time || 'N/A'}</p>
                    <p><strong>Class:</strong> ${t.class || 'N/A'}</p>
                    <p><strong>Teacher:</strong> ${t.teacher_name || 'N/A'}</p>
                  </div>
                  <div class="action-buttons">
                    <button class="btn btn-danger btn-small" onclick="deleteRecord('${t.__backendId}')">
                      <span>��️</span><span>Delete</span>
                    </button>
                  </div>
                </div>
              `).join('')}
            </div>
          `}
        </div>
      `;
      
      renderModal('timetable', getTimetableForm);
    }
    
    function renderSubjects() {
      const subjects = filterData(allData.filter(d => d.type === 'subject'));
      renderDataList('subject', subjects, [
        { key: 'title', label: 'Subject Name' },
        { key: 'grade', label: 'Grade' },
        { key: 'teacher_name', label: 'Teacher' },
        { key: 'description', label: 'Description' }
      ], getSubjectForm, '📖', 'No subjects found', 'Add curriculum subjects');
    }
    
    function renderFees() {
      const fees = filterData(allData.filter(d => d.type === 'fee'));
      renderDataList('fee', fees, [
        { key: 'student_id', label: 'Student ID' },
        { key: 'first_name', label: 'Student Name' },
        { key: 'fee_type', label: 'Fee Type' },
        { key: 'amount', label: 'Amount' },
        { key: 'due_date', label: 'Due Date' },
        { key: 'paid', label: 'Status', badge: true }
      ], getFeeForm, '💰', 'No fee records', 'Add fee record');
    }
    
    function renderExpenses() {
      const expenses = filterData(allData.filter(d => d.type === 'expense'));
      renderDataList('expense', expenses, [
        { key: 'title', label: 'Expense' },
        { key: 'category', label: 'Category' },
        { key: 'amount', label: 'Amount' },
        { key: 'created_at', label: 'Date' },
        { key: 'description', label: 'Description' }
      ], getExpenseForm, '💸', 'No expenses recorded', 'Track school expenses');
    }
    
    function renderSalaries() {
      const salaries = filterData(allData.filter(d => d.type === 'salary'));
      renderDataList('salary', salaries, [
        { key: 'teacher_id', label: 'Employee ID' },
        { key: 'teacher_name', label: 'Name' },
        { key: 'department', label: 'Department' },
        { key: 'salary', label: 'Salary' },
        { key: 'payment_date', label: 'Payment Date' }
      ], getSalaryForm, '💵', 'No salary records', 'Manage staff salaries');
    }
    
    function renderAnnouncements() {
      const announcements = filterData(allData.filter(d => d.type === 'announcement'));
      renderDataList('announcement', announcements, [
        { key: 'title', label: 'Title' },
        { key: 'announcement_text', label: 'Message' },
        { key: 'priority', label: 'Priority', badge: true },
        { key: 'created_at', label: 'Date' }
      ], getAnnouncementForm, '📢', 'No announcements', 'Create school announcement');
    }
    
    function renderEvents() {
      const events = filterData(allData.filter(d => d.type === 'event'));
      renderDataList('event', events, [
        { key: 'title', label: 'Event' },
        { key: 'event_date', label: 'Date' },
        { key: 'category', label: 'Category' },
        { key: 'location', label: 'Location' },
        { key: 'description', label: 'Description' }
      ], getEventForm, '📅', 'No events scheduled', 'Schedule new event');
    }
    
    function renderMessages() {
      const messages = filterData(allData.filter(d => d.type === 'message'));
      renderDataList('message', messages, [
        { key: 'title', label: 'Subject' },
        { key: 'description', label: 'Message' },
        { key: 'created_at', label: 'Date' }
      ], getMessageForm, '💬', 'No messages', 'Send new message');
    }
    
    function renderParents() {
      const parents = filterData(allData.filter(d => d.type === 'parent'));
      renderDataList('parent', parents, [
        { key: 'parent_name', label: 'Parent Name' },
        { key: 'student_id', label: 'Student ID' },
        { key: 'relation', label: 'Relation' },
        { key: 'phone', label: 'Phone' },
        { key: 'email', label: 'Email' }
      ], getParentForm, '👪', 'No parent records', 'Add parent information');
    }
    
    function renderLibrary() {
      const books = filterData(allData.filter(d => d.type === 'book'));
      renderDataList('book', books, [
        { key: 'book_title', label: 'Title' },
        { key: 'author', label: 'Author' },
        { key: 'isbn', label: 'ISBN' },
        { key: 'borrowed_by', label: 'Borrowed By' },
        { key: 'return_date', label: 'Return Date' }
      ], getLibraryForm, '📚', 'No books in library', 'Add book to library');
    }
    
    function renderTransport() {
      const transport = filterData(allData.filter(d => d.type === 'transport'));
      renderDataList('transport', transport, [
        { key: 'title', label: 'Route/Bus' },
        { key: 'capacity', label: 'Capacity' },
        { key: 'description', label: 'Details' }
      ], getTransportForm, '🚌', 'No transport records', 'Add transport route');
    }
    
    function renderHostel() {
      const hostel = filterData(allData.filter(d => d.type === 'hostel'));
      renderDataList('hostel', hostel, [
        { key: 'title', label: 'Room' },
        { key: 'capacity', label: 'Capacity' },
        { key: 'student_id', label: 'Occupant ID' },
        { key: 'description', label: 'Details' }
      ], getHostelForm, '🏨', 'No hostel records', 'Add hostel room');
    }
    
    function renderInventory() {
      const inventory = filterData(allData.filter(d => d.type === 'inventory'));
      renderDataList('inventory', inventory, [
        { key: 'title', label: 'Item' },
        { key: 'category', label: 'Category' },
        { key: 'capacity', label: 'Quantity' },
        { key: 'description', label: 'Description' }
      ], getInventoryForm, '��', 'No inventory items', 'Add inventory item');
    }
    
    function renderStaff() {
      const staff = filterData(allData.filter(d => d.type === 'staff'));
      renderDataList('staff', staff, [
        { key: 'teacher_name', label: 'Name' },
        { key: 'department', label: 'Department' },
        { key: 'phone', label: 'Phone' },
        { key: 'email', label: 'Email' },
        { key: 'designation', label: 'Designation' }
      ], getStaffForm, '👥', 'No staff members', 'Add staff member');
    }
    
    function renderDepartments() {
      const departments = filterData(allData.filter(d => d.type === 'department'));
      renderDataList('department', departments, [
        { key: 'title', label: 'Department' },
        { key: 'teacher_name', label: 'Head' },
        { key: 'description', label: 'Description' }
      ], getDepartmentForm, '🏢', 'No departments', 'Create department');
    }
    
    function renderLeave() {
      const leave = filterData(allData.filter(d => d.type === 'leave'));
      renderDataList('leave', leave, [
        { key: 'teacher_name', label: 'Name' },
        { key: 'created_at', label: 'From' },
        { key: 'return_date', label: 'To' },
        { key: 'description', label: 'Reason' },
        { key: 'resolved', label: 'Status', badge: true }
      ], getLeaveForm, '🗓️', 'No leave requests', 'Submit leave request');
    }
    
    function renderReports() {
      document.getElementById('contentArea').innerHTML = `
        <div class="data-section">
          <div class="section-header">
            <h2 class="section-title">
              <div class="section-title-icon">📊</div>
              <span>Reports Center</span>
            </h2>
          </div>
          
          <div class="grid-2">
            <div class="card" style="cursor: pointer;" onclick="showToast('📈 Generating student performance report...', 'success')">
              <div class="card-header">
                <div class="card-icon">📈</div>
                <div class="card-title">Student Performance</div>
              </div>
              <div class="card-text">
                <p>Comprehensive student academic performance analysis with grades, attendance, and behavioral metrics</p>
              </div>
            </div>
            
            <div class="card" style="cursor: pointer;" onclick="showToast('💰 Generating financial report...', 'success')">
              <div class="card-header">
                <div class="card-icon">💰</div>
                <div class="card-title">Financial Report</div>
              </div>
              <div class="card-text">
                <p>Detailed income, expenses, fee collection, and revenue analysis for the institution</p>
              </div>
            </div>
            
            <div class="card" style="cursor: pointer;" onclick="showToast('📋 Generating attendance report...', 'success')">
              <div class="card-header">
                <div class="card-icon">📋</div>
                <div class="card-title">Attendance Report</div>
              </div>
              <div class="card-text">
                <p>Monthly, quarterly, and yearly attendance statistics with class-wise breakdown</p>
              </div>
            </div>
            
            <div class="card" style="cursor: pointer;" onclick="showToast('📝 Generating exam analysis...', 'success')">
              <div class="card-header">
                <div class="card-icon">📝</div>
                <div class="card-title">Exam Analysis</div>
              </div>
              <div class="card-text">
                <p>Detailed exam results, grade distribution, subject-wise performance analysis</p>
              </div>
            </div>
            
            <div class="card" style="cursor: pointer;" onclick="showToast('👨‍🏫 Generating teacher report...', 'success')">
              <div class="card-header">
                <div class="card-icon">���‍🏫</div>
                <div class="card-title">Teacher Report</div>
              </div>
              <div class="card-text">
                <p>Teacher performance metrics, class assignments, and effectiveness analysis</p>
              </div>
            </div>
            
            <div class="card" style="cursor: pointer;" onclick="showToast('📚 Generating library report...', 'success')">
              <div class="card-header">
                <div class="card-icon">📚</div>
                <div class="card-title">Library Report</div>
              </div>
              <div class="card-text">
                <p>Book inventory, borrowing patterns, and library utilization statistics</p>
              </div>
            </div>
          </div>
        </div>
      `;
    }
    
    function renderAnalytics() {
      const students = allData.filter(d => d.type === 'student');
      const teachers = allData.filter(d => d.type === 'teacher');
      const fees = allData.filter(d => d.type === 'fee');
      const paidFees = fees.filter(f => f.paid);
      const totalRevenue = paidFees.reduce((sum, f) => sum + (parseFloat(f.amount) || 0), 0);
      const attendance = allData.filter(d => d.type === 'attendance');
      const presentCount = attendance.filter(a => a.present).length;
      const attendanceRate = attendance.length > 0 ? Math.round((presentCount / attendance.length) * 100) : 0;
      const collectionRate = fees.length > 0 ? Math.round((paidFees.length / fees.length) * 100) : 0;
      
      document.getElementById('contentArea').innerHTML = `
        <div class="data-section">
          <div class="section-header">
            <h2 class="section-title">
              <div class="section-title-icon">📈</div>
              <span>Analytics Dashboard</span>
            </h2>
            <div style="display: flex; gap: 10px;">
              <button class="btn btn-success" onclick="exportAllData()">
                <span>📊</span><span>Export All Data</span>
              </button>
              <button class="btn btn-warning" onclick="viewDataBreakdown()">
                <span>🔍</span><span>Data Breakdown</span>
              </button>
            </div>
          </div>
          
          <div class="stats-grid">
            <div class="stat-card">
              <div class="stat-header">
                <div class="stat-icon">👨‍🎓</div>
                <div class="stat-trend">📈 Growth</div>
              </div>
              <div class="stat-label">Student Enrollment</div>
              <div class="stat-value">${students.length}</div>
              <div class="stat-footer">Total enrolled students</div>
              <div class="progress-bar">
                <div class="progress-fill" style="width: ${Math.min((students.length / 500) * 100, 100)}%"></div>
              </div>
            </div>
            
            <div class="stat-card">
              <div class="stat-header">
                <div class="stat-icon">💰</div>
                <div class="stat-trend">💵 Revenue</div>
              </div>
              <div class="stat-label">Total Revenue</div>
              <div class="stat-value">$${totalRevenue.toLocaleString()}</div>
              <div class="stat-footer">From fee collection</div>
              <div class="progress-bar">
                <div class="progress-fill" style="width: ${collectionRate}%"></div>
              </div>
            </div>
            
            <div class="stat-card">
              <div class="stat-header">
                <div class="stat-icon">📊</div>
                <div class="stat-trend">✓ ${collectionRate}%</div>
              </div>
              <div class="stat-label">Fee Collection</div>
              <div class="stat-value">${paidFees.length}/${fees.length}</div>
              <div class="stat-footer">Fees collected</div>
              <div class="progress-bar">
                <div class="progress-fill" style="width: ${collectionRate}%"></div>
              </div>
            </div>
            
            <div class="stat-card">
              <div class="stat-header">
                <div class="stat-icon">📋</div>
                <div class="stat-trend">✓ ${attendanceRate}%</div>
              </div>
              <div class="stat-label">Attendance Rate</div>
              <div class="stat-value">${attendanceRate}%</div>
              <div class="stat-footer">Overall attendance</div>
              <div class="progress-bar">
                <div class="progress-fill" style="width: ${attendanceRate}%"></div>
              </div>
            </div>
            
            <div class="stat-card">
              <div class="stat-header">
                <div class="stat-icon">👨‍🏫</div>
                <div class="stat-trend">👥 Staff</div>
              </div>
              <div class="stat-label">Teaching Staff</div>
              <div class="stat-value">${teachers.length}</div>
              <div class="stat-footer">Active teachers</div>
              <div class="progress-bar">
                <div class="progress-fill" style="width: ${Math.min((teachers.length / 50) * 100, 100)}%"></div>
              </div>
            </div>
            
            <div class="stat-card">
              <div class="stat-header">
                <div class="stat-icon">📈</div>
                <div class="stat-trend">📊 Data</div>
              </div>
              <div class="stat-label">Total Records</div>
              <div class="stat-value">${allData.length}</div>
              <div class="stat-footer">All data entries</div>
              <div class="progress-bar">
                <div class="progress-fill" style="width: ${Math.min((allData.length / 999) * 100, 100)}%"></div>
              </div>
            </div>
          </div>
          
          <div class="grid-2">
            <div class="card">
              <div class="card-header">
                <div class="card-icon">🎯</div>
                <div class="card-title">Key Performance Indicators</div>
              </div>
              <div class="card-text">
                <p><strong>Student-Teacher Ratio:</strong> ${teachers.length > 0 ? Math.round(students.length / teachers.length) : 0}:1</p>
                <p><strong>Fee Collection Rate:</strong> ${collectionRate}%</p>
                <p><strong>Average Attendance:</strong> ${attendanceRate}%</p>
                <p><strong>Active Classes:</strong> ${allData.filter(d => d.type === 'class').length}</p>
                <p><strong>System Utilization:</strong> ${Math.round((allData.length / 999) * 100)}%</p>
              </div>
            </div>
            
            <div class="card">
              <div class="card-header">
                <div class="card-icon">💡</div>
                <div class="card-title">Insights & Recommendations</div>
              </div>
              <div class="card-text">
                <p>${students.length > 0 ? '✓ Student enrollment is active' : '⚠️ No students enrolled yet'}</p>
                <p>${teachers.length > 0 ? '✓ Teaching staff available' : '⚠️ Add teaching staff'}</p>
                <p>${attendanceRate >= 75 ? '✓ Good attendance rate' : '⚠️ Improve attendance tracking'}</p>
                <p>${collectionRate >= 70 ? '✓ Fee collection on track' : '⚠�� Follow up on pending fees'}</p>
                <p>${allData.length < 900 ? '✓ System capacity available' : '⚠️ Approaching data limit'}</p>
              </div>
            </div>
          </div>
        </div>
      `;
    }
    
    function renderComplaints() {
      const complaints = filterData(allData.filter(d => d.type === 'complaint'));
      renderDataList('complaint', complaints, [
        { key: 'title', label: 'Subject' },
        { key: 'complaint_text', label: 'Complaint' },
        { key: 'category', label: 'Category' },
        { key: 'resolved', label: 'Status', badge: true },
        { key: 'created_at', label: 'Date' }
      ], getComplaintForm, '📝', 'No complaints', 'Submit feedback or complaint');
    }
    
    function renderSettings() {
      const config = window.elementSdk ? window.elementSdk.config : defaultConfig;
      
      document.getElementById('contentArea').innerHTML = `
        <div class="data-section">
          <div class="section-header">
            <h2 class="section-title">
              <div class="section-title-icon">⚙️</div>
              <span>System Settings</span>
            </h2>
          </div>
          
          <div class="data-section" style="margin-bottom: 30px;">
            <h3 style="font-size: 20px; font-weight: 900; margin-bottom: 20px; color: #1f2937; display: flex; align-items: center; gap: 10px;">
              <span style="font-size: 28px;">🏫</span>
              <span>School Branding</span>
            </h3>
            <form id="settingsForm">
              <div class="form-grid">
                <div class="form-group form-group-full">
                  <label class="form-label" for="schoolNameSetting">School Name</label>
                  <input type="text" id="schoolNameSetting" class="form-input" value="${config.school_name || defaultConfig.school_name}">
                  <div style="margin-top: 6px; font-size: 12px; color: #6b7280; font-weight: 600;">
                    This appears on the login screen and sidebar
                  </div>
                </div>
                
                <div class="form-group form-group-full">
                  <label class="form-label" for="schoolTaglineSetting">School Tagline</label>
                  <input type="text" id="schoolTaglineSetting" class="form-input" value="${config.school_tagline || defaultConfig.school_tagline}">
                  <div style="margin-top: 6px; font-size: 12px; color: #6b7280; font-weight: 600;">
                    Displayed under the school name
                  </div>
                </div>
                
                <div class="form-group form-group-full">
                  <label class="form-label" for="welcomeMessageSetting">Dashboard Welcome Message</label>
                  <input type="text" id="welcomeMessageSetting" class="form-input" value="${config.welcome_message || defaultConfig.welcome_message}">
                  <div style="margin-top: 6px; font-size: 12px; color: #6b7280; font-weight: 600;">
                    The main heading shown on the dashboard
                  </div>
                </div>
                
                <div class="form-group">
                  <label class="form-label" for="systemVersionSetting">System Version Label</label>
                  <input type="text" id="systemVersionSetting" class="form-input" value="${config.system_version || defaultConfig.system_version}">
                  <div style="margin-top: 6px; font-size: 12px; color: #6b7280; font-weight: 600;">
                    Version badge displayed on login and sidebar
                  </div>
                </div>
              </div>
              
              <div style="margin-top: 25px; padding-top: 20px; border-top: 2px solid #f3f4f6;">
                <button type="submit" class="btn btn-primary" id="saveSettingsBtn">
                  <span>💾</span><span>Save Settings</span>
                </button>
                <button type="button" class="btn btn-secondary" onclick="resetSettings()" style="margin-left: 10px;">
                  <span>🔄</span><span>Reset to Defaults</span>
                </button>
              </div>
            </form>
          </div>
          
          <div class="grid-2">
            <div class="card">
              <div class="card-header">
                <div class="card-icon">📊</div>
                <div class="card-title">System Statistics</div>
              </div>
              <div class="card-text">
                <p><strong>Total Modules:</strong> 30 Complete Modules</p>
                <p><strong>Data Records:</strong> ${allData.length} / 999</p>
                <p><strong>Storage Used:</strong> ${Math.round((allData.length / 999) * 100)}%</p>
                <p><strong>Last Updated:</strong> ${new Date().toLocaleString()}</p>
                <p><strong>Status:</strong> ✅ All Systems Operational</p>
              </div>
            </div>
            
            <div class="card">
              <div class="card-header">
                <div class="card-icon">🎨</div>
                <div class="card-title">Customization Options</div>
              </div>
              <div class="card-text">
                <p>✏️ Edit school branding above</p>
                <p>🎨 Use Canva's edit panel for more options</p>
                <p>📝 Update welcome messages instantly</p>
                <p>⚙️ All settings save automatically</p>
                <p>💾 Changes persist in your Canva design</p>
              </div>
            </div>
            
            <div class="card">
              <div class="card-header">
                <div class="card-icon">🚀</div>
                <div class="card-title">System Features</div>
              </div>
              <div class="card-text">
                <p>✅ Real-time data synchronization</p>
                <p>✅ Advanced search & filtering</p>
                <p>✅ Fully responsive design</p>
                <p>✅ Modern gradient UI</p>
                <p>✅ 30 comprehensive modules</p>
              </div>
            </div>
            
            <div class="card">
              <div class="card-header">
                <div class="card-icon">📚</div>
                <div class="card-title">Quick Tips</div>
              </div>
              <div class="card-text">
                <p>💡 Use the edit panel for text customization</p>
                <p>🔍 Global search works across all modules</p>
                <p>📊 Check Analytics for detailed insights</p>
                <p>💾 All data saves to your Canva Sheet</p>
                <p>🎓 Perfect for schools of any size</p>
              </div>
            </div>
          </div>
        </div>
      `;
      
      document.getElementById('settingsForm').onsubmit = async function(e) {
        e.preventDefault();
        
        if (!window.elementSdk) {
          showToast('���️ Settings SDK not available', 'warning');
          return;
        }
        
        const btn = document.getElementById('saveSettingsBtn');
        const originalHTML = btn.innerHTML;
        btn.innerHTML = '<span>⏳</span><span>Saving...</span>';
        btn.disabled = true;
        
        const newConfig = {
          school_name: document.getElementById('schoolNameSetting').value,
          school_tagline: document.getElementById('schoolTaglineSetting').value,
          welcome_message: document.getElementById('welcomeMessageSetting').value,
          system_version: document.getElementById('systemVersionSetting').value
        };
        
        await window.elementSdk.setConfig(newConfig);
        
        btn.innerHTML = originalHTML;
        btn.disabled = false;
        
        showToast('✅ Settings saved successfully!', 'success');
      };
    }
    
    function resetSettings() {
      if (!window.elementSdk) {
        showToast('⚠️ Settings SDK not available', 'warning');
        return;
      }
      
      document.getElementById('schoolNameSetting').value = defaultConfig.school_name;
      document.getElementById('schoolTaglineSetting').value = defaultConfig.school_tagline;
      document.getElementById('welcomeMessageSetting').value = defaultConfig.welcome_message;
      document.getElementById('systemVersionSetting').value = defaultConfig.system_version;
      
      window.elementSdk.setConfig(defaultConfig);
      showToast('🔄 Settings reset to defaults!', 'success');
    }
    
    function renderDataList(type, data, columns, formGetter, icon, emptyText, emptySubtext) {
      let html = `
        <div class="data-section">
          <div class="section-header">
            <h2 class="section-title">
              <div class="section-title-icon">${icon}</div>
              <span>${getPageInfo(type + 's').title}</span>
            </h2>
            <button class="btn btn-primary" onclick="openModal('${type}')">
              <span>➕</span><span>Add ${type.charAt(0).toUpperCase() + type.slice(1)}</span>
            </button>
          </div>
          
          ${data.length > 0 ? `
            <div class="filter-bar">
              <input type="text" class="search-input" placeholder="Search ${type}s..." oninput="handleSearch(event)">
              <span style="color: #6b7280; font-weight: 700; font-size: 14px;">
                ${data.length} ${type}${data.length !== 1 ? 's' : ''} found
              </span>
            </div>
          ` : ''}
      `;
      
      if (data.length === 0) {
        html += `
          <div class="empty-state">
            <div class="empty-icon">${icon}</div>
            <div class="empty-text">${emptyText}</div>
            <div class="empty-subtext">${emptySubtext}</div>
            <button class="btn btn-primary" onclick="openModal('${type}')" style="margin-top: 20px;">
              <span>➕</span><span>Add ${type.charAt(0).toUpperCase() + type.slice(1)}</span>
            </button>
          </div>
        `;
      } else {
        html += `
          <div style="overflow-x: auto;">
            <table class="data-table">
              <thead>
                <tr>
                  ${columns.map(col => `<th>${col.label}</th>`).join('')}
                  <th>Actions</th>
                </tr>
              </thead>
              <tbody>
        `;
        
        data.forEach(item => {
          html += `<tr>`;
          columns.forEach(col => {
            let value = item[col.key] || '-';
            if (col.badge) {
              const badgeClass = getBadgeClass(value);
              value = `<span class="badge ${badgeClass}">${formatBadgeValue(value)}</span>`;
            }
            html += `<td>${value}</td>`;
          });
          html += `
            <td>
              <div class="action-buttons">
                <button class="btn btn-danger btn-small" onclick="deleteRecord('${item.__backendId}')">
                  <span>🗑️</span>
                </button>
              </div>
            </td>
          </tr>`;
        });
        
        html += `</tbody></table></div>`;
      }
      
      html += `</div>`;
      document.getElementById('contentArea').innerHTML = html;
      renderModal(type, formGetter);
    }
    
    function handleSearch(event) {
      searchQuery = event.target.value.toLowerCase();
      renderCurrentPage();
    }
    
    function getBadgeClass(value) {
      if (value === 'active' || value === true || value === 'High' || value === 'Approved') return 'badge-success';
      if (value === 'inactive' || value === false || value === 'Low' || value === 'Rejected') return 'badge-danger';
      if (value === 'Medium' || value === 'Pending') return 'badge-warning';
      return 'badge-info';
    }
    
    function formatBadgeValue(value) {
      if (value === true) return 'Yes';
      if (value === false) return 'No';
      return value;
    }
    
    function getStudentForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="studentId">Student ID *</label>
            <input type="text" id="studentId" class="form-input" required placeholder="e.g., STU2024001">
          </div>
          <div class="form-group">
            <label class="form-label" for="firstName">First Name *</label>
            <input type="text" id="firstName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="lastName">Last Name *</label>
            <input type="text" id="lastName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="gender">Gender *</label>
            <select id="gender" class="form-select" required>
              <option value="">Select Gender</option>
              <option value="Male">Male</option>
              <option value="Female">Female</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="dob">Date of Birth *</label>
            <input type="date" id="dob" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="admissionDate">Enrolled Date *</label>
            <input type="date" id="admissionDate" class="form-input" required value="${new Date().toISOString().split('T')[0]}">
          </div>
          <div class="form-group">
            <label class="form-label" for="grade">Grade *</label>
            <select id="grade" class="form-select" required onchange="updateSectionOptions()">
              <option value="">Select Grade</option>
              <option value="K1">K1 (Kindergarten 1)</option>
              <option value="K2">K2 (Kindergarten 2)</option>
              <option value="K3">K3 (Kindergarten 3)</option>
              <option value="G1">G1 (Grade 1)</option>
              <option value="G2">G2 (Grade 2)</option>
              <option value="G3">G3 (Grade 3)</option>
              <option value="G4">G4 (Grade 4)</option>
              <option value="G5">G5 (Grade 5)</option>
              <option value="G6">G6 (Grade 6)</option>
              <option value="G7">G7 (Grade 7)</option>
              <option value="G8">G8 (Grade 8)</option>
              <option value="G9">G9 (Grade 9)</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="classField">Section (A/B) *</label>
            <select id="classField" class="form-select" required>
              <option value="">Select Section</option>
              <option value="A">Section A</option>
              <option value="B">Section B</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="shift">Session Time *</label>
            <select id="shift" class="form-select" required>
              <option value="">Select Session</option>
              <option value="AM">AM (Morning)</option>
              <option value="PM">PM (Afternoon)</option>
              <option value="Both">Both Sessions</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="village">Village *</label>
            <input type="text" id="village" class="form-input" required placeholder="Enter village name">
          </div>
          <div class="form-group">
            <label class="form-label" for="commune">Commune *</label>
            <input type="text" id="commune" class="form-input" required placeholder="Enter commune name">
          </div>
          <div class="form-group">
            <label class="form-label" for="district">District *</label>
            <input type="text" id="district" class="form-input" required placeholder="Enter district name">
          </div>
          <div class="form-group">
            <label class="form-label" for="province">Province *</label>
            <input type="text" id="province" class="form-input" required placeholder="Enter province name">
          </div>
          <div class="form-group">
            <label class="form-label" for="guardianName">Guardian Name</label>
            <input type="text" id="guardianName" class="form-input" placeholder="Parent/Guardian name">
          </div>
          <div class="form-group">
            <label class="form-label" for="guardianPhone">Guardian Phone</label>
            <input type="tel" id="guardianPhone" class="form-input" placeholder="Contact number">
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="photoUrl">Student Photo</label>
            <div style="display: flex; gap: 10px; align-items: center;">
              <input type="file" id="photoFile" accept="image/*" style="display: none;" onchange="handlePhotoUpload(event, 'photoUrl')">
              <button type="button" class="btn btn-secondary btn-small" onclick="document.getElementById('photoFile').click()">
                <span>📷</span><span>Upload from Device</span>
              </button>
              <input type="url" id="photoUrl" class="form-input" placeholder="Or enter photo URL (https://...)" style="flex: 1;">
            </div>
            <div id="photoPreview" style="margin-top: 12px; display: none;">
              <img id="photoPreviewImg" style="max-width: 150px; max-height: 150px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.15);">
            </div>
            <div style="margin-top: 8px; font-size: 12px; color: #6b7280; font-weight: 600;">
              💡 Upload a photo from your device or paste a URL
            </div>
          </div>
          <div class="form-group">
            <label class="form-label" for="bloodGroup">Blood Group</label>
            <select id="bloodGroup" class="form-select">
              <option value="">Select Blood Group</option>
              <option value="A+">A+</option>
              <option value="A-">A-</option>
              <option value="B+">B+</option>
              <option value="B-">B-</option>
              <option value="AB+">AB+</option>
              <option value="AB-">AB-</option>
              <option value="O+">O+</option>
              <option value="O-">O-</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="nationality">Nationality</label>
            <input type="text" id="nationality" class="form-input" placeholder="e.g., Cambodian" value="Cambodian">
          </div>
          <div class="form-group">
            <label class="form-label" for="religion">Religion</label>
            <input type="text" id="religion" class="form-input" placeholder="e.g., Buddhism">
          </div>
          <div class="form-group">
            <label class="form-label" for="emergencyContact">Emergency Contact</label>
            <input type="tel" id="emergencyContact" class="form-input" placeholder="Emergency phone number">
          </div>
          <div class="form-group">
            <label class="form-label" for="previousSchool">Previous School</label>
            <input type="text" id="previousSchool" class="form-input" placeholder="Name of previous school">
          </div>
          <div class="form-group">
            <label class="form-label" for="medicalConditions">Medical Conditions</label>
            <input type="text" id="medicalConditions" class="form-input" placeholder="Any medical conditions">
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="notes">Additional Notes</label>
            <textarea id="notes" class="form-textarea" placeholder="Any additional information about the student"></textarea>
          </div>
        </div>
      `;
    }
    
    function getTeacherForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="teacherId">Teacher ID *</label>
            <input type="text" id="teacherId" class="form-input" required placeholder="e.g., TCH2024001">
          </div>
          <div class="form-group">
            <label class="form-label" for="teacherName">Full Name *</label>
            <input type="text" id="teacherName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="gender">Gender *</label>
            <select id="gender" class="form-select" required>
              <option value="">Select Gender</option>
              <option value="Male">Male</option>
              <option value="Female">Female</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="dob">Date of Birth</label>
            <input type="date" id="dob" class="form-input">
          </div>
          <div class="form-group">
            <label class="form-label" for="subject">Subject/Specialization *</label>
            <input type="text" id="subject" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="department">Department</label>
            <input type="text" id="department" class="form-input" placeholder="e.g., Science, Mathematics">
          </div>
          <div class="form-group">
            <label class="form-label" for="email">Email *</label>
            <input type="email" id="email" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="phone">Phone *</label>
            <input type="tel" id="phone" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="emergencyContact">Emergency Contact</label>
            <input type="tel" id="emergencyContact" class="form-input" placeholder="Emergency phone number">
          </div>
          <div class="form-group">
            <label class="form-label" for="qualification">Highest Qualification *</label>
            <select id="qualification" class="form-select" required>
              <option value="">Select Qualification</option>
              <option value="High School">High School Diploma</option>
              <option value="Associate">Associate Degree</option>
              <option value="Bachelor">Bachelor's Degree</option>
              <option value="Master">Master's Degree</option>
              <option value="PhD">PhD/Doctorate</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="experience">Experience (years)</label>
            <input type="number" id="experience" class="form-input" min="0">
          </div>
          <div class="form-group">
            <label class="form-label" for="joiningDate">Joining Date *</label>
            <input type="date" id="joiningDate" class="form-input" required value="${new Date().toISOString().split('T')[0]}">
          </div>
          <div class="form-group">
            <label class="form-label" for="salary">Monthly Salary</label>
            <input type="number" id="salary" class="form-input" placeholder="USD amount">
          </div>
          <div class="form-group">
            <label class="form-label" for="designation">Designation</label>
            <select id="designation" class="form-select">
              <option value="">Select Designation</option>
              <option value="Teacher">Teacher</option>
              <option value="Senior Teacher">Senior Teacher</option>
              <option value="Head of Department">Head of Department</option>
              <option value="Vice Principal">Vice Principal</option>
              <option value="Principal">Principal</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="bloodGroup">Blood Group</label>
            <select id="bloodGroup" class="form-select">
              <option value="">Select Blood Group</option>
              <option value="A+">A+</option>
              <option value="A-">A-</option>
              <option value="B+">B+</option>
              <option value="B-">B-</option>
              <option value="AB+">AB+</option>
              <option value="AB-">AB-</option>
              <option value="O+">O+</option>
              <option value="O-">O-</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="nationality">Nationality</label>
            <input type="text" id="nationality" class="form-input" placeholder="e.g., Cambodian" value="Cambodian">
          </div>
          <div class="form-group">
            <label class="form-label" for="maritalStatus">Marital Status</label>
            <select id="maritalStatus" class="form-select">
              <option value="">Select Status</option>
              <option value="Single">Single</option>
              <option value="Married">Married</option>
              <option value="Divorced">Divorced</option>
              <option value="Widowed">Widowed</option>
            </select>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="address">Full Address</label>
            <textarea id="address" class="form-textarea" placeholder="Village, Commune, District, Province"></textarea>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="photoUrl">Teacher Photo</label>
            <div style="display: flex; gap: 10px; align-items: center;">
              <input type="file" id="photoFile" accept="image/*" style="display: none;" onchange="handlePhotoUpload(event, 'photoUrl')">
              <button type="button" class="btn btn-secondary btn-small" onclick="document.getElementById('photoFile').click()">
                <span>📷</span><span>Upload from Device</span>
              </button>
              <input type="url" id="photoUrl" class="form-input" placeholder="Or enter photo URL (https://...)" style="flex: 1;">
            </div>
            <div id="photoPreview" style="margin-top: 12px; display: none;">
              <img id="photoPreviewImg" style="max-width: 150px; max-height: 150px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.15);">
            </div>
            <div style="margin-top: 8px; font-size: 12px; color: #6b7280; font-weight: 600;">
              💡 Upload a photo from your device or paste a URL
            </div>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="notes">Additional Notes</label>
            <textarea id="notes" class="form-textarea" placeholder="Certifications, awards, special skills, etc."></textarea>
          </div>
        </div>
      `;
    }
    
    function getClassForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="className">Class Name *</label>
            <input type="text" id="className" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="grade">Grade *</label>
            <input type="text" id="grade" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="roomNumber">Room Number *</label>
            <input type="text" id="roomNumber" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="capacity">Capacity *</label>
            <input type="number" id="capacity" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="teacherName">Class Teacher</label>
            <input type="text" id="teacherName" class="form-input">
          </div>
        </div>
      `;
    }
    
    function getAttendanceForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="attendanceDate">Date *</label>
            <input type="date" id="attendanceDate" class="form-input" required value="${new Date().toISOString().split('T')[0]}">
          </div>
          <div class="form-group">
            <label class="form-label" for="studentId">Student ID *</label>
            <input type="text" id="studentId" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="firstName">Student Name *</label>
            <input type="text" id="firstName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="classField">Class *</label>
            <input type="text" id="classField" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="present">Attendance Status *</label>
            <select id="present" class="form-select" required>
              <option value="true">Present</option>
              <option value="false">Absent</option>
            </select>
          </div>
        </div>
      `;
    }
    
    function getExamForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="examName">Exam Name *</label>
            <input type="text" id="examName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="studentId">Student ID *</label>
            <input type="text" id="studentId" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="subject">Subject *</label>
            <input type="text" id="subject" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="score">Score *</label>
            <input type="number" id="score" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="totalMarks">Total Marks *</label>
            <input type="number" id="totalMarks" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="grade">Grade</label>
            <input type="text" id="grade" class="form-input">
          </div>
        </div>
      `;
    }
    
    function getAssignmentForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="assignmentTitle">Title *</label>
            <input type="text" id="assignmentTitle" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="subject">Subject *</label>
            <input type="text" id="subject" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="classField">Class *</label>
            <input type="text" id="classField" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="dueDate">Due Date *</label>
            <input type="date" id="dueDate" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Description</label>
            <textarea id="description" class="form-textarea"></textarea>
          </div>
        </div>
      `;
    }
    
    function getTimetableForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="subject">Subject *</label>
            <input type="text" id="subject" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="dayOfWeek">Day *</label>
            <select id="dayOfWeek" class="form-select" required>
              <option value="">Select</option>
              <option value="Monday">Monday</option>
              <option value="Tuesday">Tuesday</option>
              <option value="Wednesday">Wednesday</option>
              <option value="Thursday">Thursday</option>
              <option value="Friday">Friday</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="startTime">Start Time *</label>
            <input type="time" id="startTime" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="endTime">End Time *</label>
            <input type="time" id="endTime" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="classField">Class *</label>
            <input type="text" id="classField" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="teacherName">Teacher</label>
            <input type="text" id="teacherName" class="form-input">
          </div>
        </div>
      `;
    }
    
    function getSubjectForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="title">Subject Name *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="grade">Grade *</label>
            <input type="text" id="grade" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="teacherName">Teacher</label>
            <input type="text" id="teacherName" class="form-input">
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Description</label>
            <textarea id="description" class="form-textarea"></textarea>
          </div>
        </div>
      `;
    }
    
    function getFeeForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="studentId">Student ID *</label>
            <input type="text" id="studentId" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="firstName">Student Name *</label>
            <input type="text" id="firstName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="feeType">Fee Type *</label>
            <select id="feeType" class="form-select" required>
              <option value="">Select</option>
              <option value="Tuition">Tuition</option>
              <option value="Transport">Transport</option>
              <option value="Library">Library</option>
              <option value="Sports">Sports</option>
              <option value="Lab">Lab</option>
              <option value="Other">Other</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="amount">Amount *</label>
            <input type="number" id="amount" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="dueDate">Due Date *</label>
            <input type="date" id="dueDate" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="paid">Payment Status *</label>
            <select id="paid" class="form-select" required>
              <option value="false">Unpaid</option>
              <option value="true">Paid</option>
            </select>
          </div>
        </div>
      `;
    }
    
    function getExpenseForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="title">Expense Name *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="category">Category *</label>
            <select id="category" class="form-select" required>
              <option value="">Select</option>
              <option value="Utilities">Utilities</option>
              <option value="Maintenance">Maintenance</option>
              <option value="Supplies">Supplies</option>
              <option value="Salaries">Salaries</option>
              <option value="Transport">Transport</option>
              <option value="Other">Other</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="amount">Amount *</label>
            <input type="number" id="amount" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Description</label>
            <textarea id="description" class="form-textarea"></textarea>
          </div>
        </div>
      `;
    }
    
    function getSalaryForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="teacherId">Employee ID *</label>
            <input type="text" id="teacherId" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="teacherName">Name *</label>
            <input type="text" id="teacherName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="department">Department *</label>
            <input type="text" id="department" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="salary">Salary Amount *</label>
            <input type="number" id="salary" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="paymentDate">Payment Date *</label>
            <input type="date" id="paymentDate" class="form-input" required>
          </div>
        </div>
      `;
    }
    
    function getAnnouncementForm() {
      return `
        <div class="form-grid">
          <div class="form-group form-group-full">
            <label class="form-label" for="title">Title *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="announcementText">Message *</label>
            <textarea id="announcementText" class="form-textarea" required></textarea>
          </div>
          <div class="form-group">
            <label class="form-label" for="priority">Priority *</label>
            <select id="priority" class="form-select" required>
              <option value="Low">Low</option>
              <option value="Medium">Medium</option>
              <option value="High">High</option>
            </select>
          </div>
        </div>
      `;
    }
    
    function getEventForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="title">Event Name *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="eventDate">Date *</label>
            <input type="date" id="eventDate" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="category">Category</label>
            <select id="category" class="form-select">
              <option value="Academic">Academic</option>
              <option value="Sports">Sports</option>
              <option value="Cultural">Cultural</option>
              <option value="Other">Other</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="location">Location</label>
            <input type="text" id="location" class="form-input">
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Description</label>
            <textarea id="description" class="form-textarea"></textarea>
          </div>
        </div>
      `;
    }
    
    function getMessageForm() {
      return `
        <div class="form-grid">
          <div class="form-group form-group-full">
            <label class="form-label" for="title">Subject *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Message *</label>
            <textarea id="description" class="form-textarea" required></textarea>
          </div>
        </div>
      `;
    }
    
    function getParentForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="parentName">Parent Name *</label>
            <input type="text" id="parentName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="studentId">Student ID *</label>
            <input type="text" id="studentId" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="relation">Relation *</label>
            <select id="relation" class="form-select" required>
              <option value="Father">Father</option>
              <option value="Mother">Mother</option>
              <option value="Guardian">Guardian</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label" for="phone">Phone *</label>
            <input type="tel" id="phone" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="email">Email</label>
            <input type="email" id="email" class="form-input">
          </div>
        </div>
      `;
    }
    
    function getLibraryForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="bookTitle">Book Title *</label>
            <input type="text" id="bookTitle" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="author">Author *</label>
            <input type="text" id="author" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="isbn">ISBN</label>
            <input type="text" id="isbn" class="form-input">
          </div>
          <div class="form-group">
            <label class="form-label" for="borrowedBy">Borrowed By</label>
            <input type="text" id="borrowedBy" class="form-input">
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="returnDate">Return Date</label>
            <input type="date" id="returnDate" class="form-input">
          </div>
        </div>
      `;
    }
    
    function getTransportForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="title">Route/Bus Number *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="capacity">Capacity *</label>
            <input type="number" id="capacity" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Route Details</label>
            <textarea id="description" class="form-textarea"></textarea>
          </div>
        </div>
      `;
    }
    
    function getHostelForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="title">Room Number *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="capacity">Capacity *</label>
            <input type="number" id="capacity" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="studentId">Occupant Student ID</label>
            <input type="text" id="studentId" class="form-input">
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Details</label>
            <textarea id="description" class="form-textarea"></textarea>
          </div>
        </div>
      `;
    }
    
    function getInventoryForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="title">Item Name *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="category">Category *</label>
            <input type="text" id="category" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="capacity">Quantity *</label>
            <input type="number" id="capacity" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Description</label>
            <textarea id="description" class="form-textarea"></textarea>
          </div>
        </div>
      `;
    }
    
    function getStaffForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="teacherName">Name *</label>
            <input type="text" id="teacherName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="department">Department *</label>
            <input type="text" id="department" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="designation">Designation</label>
            <input type="text" id="designation" class="form-input">
          </div>
          <div class="form-group">
            <label class="form-label" for="phone">Phone *</label>
            <input type="tel" id="phone" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="email">Email</label>
            <input type="email" id="email" class="form-input">
          </div>
        </div>
      `;
    }
    
    function getDepartmentForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="title">Department Name *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="teacherName">Department Head</label>
            <input type="text" id="teacherName" class="form-input">
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Description</label>
            <textarea id="description" class="form-textarea"></textarea>
          </div>
        </div>
      `;
    }
    
    function getLeaveForm() {
      return `
        <div class="form-grid">
          <div class="form-group">
            <label class="form-label" for="teacherName">Name *</label>
            <input type="text" id="teacherName" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="createdAt">From Date *</label>
            <input type="date" id="createdAt" class="form-input" required>
          </div>
          <div class="form-group">
            <label class="form-label" for="returnDate">To Date *</label>
            <input type="date" id="returnDate" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="description">Reason *</label>
            <textarea id="description" class="form-textarea" required></textarea>
          </div>
        </div>
      `;
    }
    
    function getComplaintForm() {
      return `
        <div class="form-grid">
          <div class="form-group form-group-full">
            <label class="form-label" for="title">Subject *</label>
            <input type="text" id="title" class="form-input" required>
          </div>
          <div class="form-group form-group-full">
            <label class="form-label" for="complaintText">Complaint *</label>
            <textarea id="complaintText" class="form-textarea" required></textarea>
          </div>
          <div class="form-group">
            <label class="form-label" for="category">Category *</label>
            <select id="category" class="form-select" required>
              <option value="Academic">Academic</option>
              <option value="Infrastructure">Infrastructure</option>
              <option value="Staff">Staff</option>
              <option value="Other">Other</option>
            </select>
          </div>
        </div>
      `;
    }
    
    function renderModal(type, formGetter) {
      const formFields = formGetter();
      const typeLabel = type.charAt(0).toUpperCase() + type.slice(1);
      const icon = getTypeIcon(type);
      
      document.getElementById('modalContainer').innerHTML = `
        <div class="modal-overlay" id="${type}Modal">
          <div class="modal">
            <h2 class="modal-header">
              <div class="modal-icon">${icon}</div>
              <span>Add ${typeLabel}</span>
            </h2>
            <form id="${type}Form">
              ${formFields}
              <div class="form-actions">
                <button type="button" class="btn btn-secondary" onclick="closeModal('${type}')">
                  <span>✖</span><span>Cancel</span>
                </button>
                <button type="submit" class="btn btn-primary" id="${type}SubmitBtn">
                  <span>💾</span><span>Save</span>
                </button>
              </div>
            </form>
          </div>
        </div>
      `;
      
      document.getElementById(`${type}Form`).onsubmit = function(e) {
        handleSubmit(e, type);
      };
    }
    
    function getTypeIcon(type) {
      const icons = {
        student: '👨‍🎓', teacher: '👨‍🏫', class: '🏫', attendance: '📋',
        exam: '📝', assignment: '📚', timetable: '⏰', subject: '📖', fee: '💰',
        expense: '💸', salary: '💵', announcement: '���', event: '📅',
        message: '💬', parent: '👪', book: '📚', transport: '🚌',
        hostel: '🏨', inventory: '📦', staff: '👥', department: '🏢',
        leave: '🗓️', complaint: '📝'
      };
      return icons[type] || '📄';
    }
    
    function openModal(type) {
      document.getElementById(`${type}Modal`).classList.add('active');
    }
    
    function closeModal(type) {
      document.getElementById(`${type}Modal`).classList.remove('active');
      document.getElementById(`${type}Form`).reset();
    }
    
    async function handleSubmit(event, type) {
      event.preventDefault();
      
      if (allData.length >= 999) {
        showToast('⚠️ Maximum limit of 999 records reached! Please delete some records first.', 'error');
        return;
      }
      
      const btn = document.getElementById(`${type}SubmitBtn`);
      const originalHTML = btn.innerHTML;
      btn.innerHTML = '<span>⏳</span><span>Saving...</span>';
      btn.disabled = true;
      
      const record = {
        type: type,
        id: Date.now().toString(),
        created_at: new Date().toISOString(),
        status: 'active'
      };
      
      const form = document.getElementById(`${type}Form`);
      const inputs = form.querySelectorAll('input, select, textarea');
      inputs.forEach(input => {
        let value = input.value;
        if (input.type === 'number') {
          value = parseFloat(value) || 0;
        } else if (input.type === 'checkbox') {
          value = input.checked;
        } else if (input.id === 'present' || input.id === 'paid' || input.id === 'submitted' || input.id === 'resolved') {
          value = value === 'true';
        }
        
        const key = input.id.replace(/([A-Z])/g, '_$1').toLowerCase();
        record[key] = value;
      });
      
      if (type === 'student') {
        record.student_code = 'STU' + Date.now().toString().slice(-6);
      }
      
      const result = await window.dataSdk.create(record);
      
      btn.innerHTML = originalHTML;
      btn.disabled = false;
      
      if (result.isOk) {
        showToast(`✅ ${typeLabel} added successfully!`, 'success');
        closeModal(type);
      } else {
        showToast('❌ Failed to save. Please try again.', 'error');
      }
    }
    
    async function deleteRecord(backendId) {
      const record = allData.find(d => d.__backendId === backendId);
      if (!record) return;
      
      const result = await window.dataSdk.delete(record);
      
      if (result.isOk) {
        showToast('✅ Record deleted successfully!', 'success');
      } else {
        showToast('❌ Failed to delete. Please try again.', 'error');
      }
    }
    
    function handlePhotoUpload(event, targetInputId) {
      const file = event.target.files[0];
      if (!file) return;
      
      if (!file.type.startsWith('image/')) {
        showToast('⚠️ Please select an image file', 'warning');
        return;
      }
      
      if (file.size > 5 * 1024 * 1024) {
        showToast('⚠️ Image must be less than 5MB', 'warning');
        return;
      }
      
      const reader = new FileReader();
      reader.onload = function(e) {
        const base64String = e.target.result;
        document.getElementById(targetInputId).value = base64String;
        
        const preview = document.getElementById('photoPreview');
        const previewImg = document.getElementById('photoPreviewImg');
        if (preview && previewImg) {
          previewImg.src = base64String;
          preview.style.display = 'block';
        }
        
        showToast('✅ Photo uploaded successfully!', 'success');
      };
      reader.onerror = function() {
        showToast('❌ Failed to read image file', 'error');
      };
      reader.readAsDataURL(file);
    }
    
    function showToast(message, type = 'success') {
      const toast = document.getElementById('toast');
      const icon = type === 'success' ? '✅' : type === 'error' ? '❌' : '⚠️';
      toast.innerHTML = `<span class="toast-icon">${icon}</span><span>${message}</span>`;
      toast.className = `toast show ${type}`;
      
      setTimeout(() => {
        toast.classList.remove('show');
      }, 3500);
    }
    
    function exportAllData() {
      if (allData.length === 0) {
        showToast('⚠️ No data to export!', 'warning');
        return;
      }
      
      const dataByType = {};
      allData.forEach(record => {
        const type = record.type || 'unknown';
        if (!dataByType[type]) {
          dataByType[type] = [];
        }
        dataByType[type].push(record);
      });
      
      let csvContent = '';
      
      Object.keys(dataByType).forEach(type => {
        csvContent += `\n\n=== ${type.toUpperCase()} (${dataByType[type].length} records) ===\n`;
        
        if (dataByType[type].length > 0) {
          const headers = Object.keys(dataByType[type][0]).filter(k => k !== '__backendId');
          csvContent += headers.join(',') + '\n';
          
          dataByType[type].forEach(record => {
            const values = headers.map(h => {
              let val = record[h];
              if (val === null || val === undefined) val = '';
              if (typeof val === 'string' && val.includes(',')) {
                val = `"${val}"`;
              }
              return val;
            });
            csvContent += values.join(',') + '\n';
          });
        }
      });
      
      const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
      const link = document.createElement('a');
      const url = URL.createObjectURL(blob);
      link.setAttribute('href', url);
      link.setAttribute('download', `school_data_export_${new Date().toISOString().split('T')[0]}.csv`);
      link.style.visibility = 'hidden';
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
      
      showToast(`✅ Exported ${allData.length} records successfully!`, 'success');
    }
    
    function viewDataBreakdown() {
      const breakdown = {};
      allData.forEach(record => {
        const type = record.type || 'unknown';
        breakdown[type] = (breakdown[type] || 0) + 1;
      });
      
      const sortedTypes = Object.keys(breakdown).sort((a, b) => breakdown[b] - breakdown[a]);
      
      let html = `
        <div class="data-section">
          <div class="section-header">
            <h2 class="section-title">
              <div class="section-title-icon">🔍</div>
              <span>Data Breakdown</span>
            </h2>
            <button class="btn btn-secondary" onclick="renderAnalytics()">
              <span>◀</span><span>Back to Analytics</span>
            </button>
          </div>
          
          <div class="card" style="margin-bottom: 25px;">
            <div class="card-header">
              <div class="card-icon">📊</div>
              <div class="card-title">Total Records: ${allData.length} / 999</div>
            </div>
            <div class="card-text">
              <p><strong>Storage Used:</strong> ${Math.round((allData.length / 999) * 100)}%</p>
              <p><strong>Available Space:</strong> ${999 - allData.length} records remaining</p>
              <p><strong>Data Types:</strong> ${Object.keys(breakdown).length} different types</p>
            </div>
            <div class="progress-bar">
              <div class="progress-fill" style="width: ${Math.round((allData.length / 999) * 100)}%"></div>
            </div>
          </div>
          
          <div class="stats-grid">
      `;
      
      sortedTypes.forEach(type => {
        const count = breakdown[type];
        const percentage = Math.round((count / allData.length) * 100);
        const icon = getTypeIcon(type);
        
        html += `
          <div class="stat-card" onclick="switchPage('${type}s')">
            <div class="stat-header">
              <div class="stat-icon">${icon}</div>
              <div class="stat-trend">${percentage}%</div>
            </div>
            <div class="stat-label">${type.charAt(0).toUpperCase() + type.slice(1)}s</div>
            <div class="stat-value">${count}</div>
            <div class="stat-footer">${count} ${type} record${count !== 1 ? 's' : ''}</div>
            <div class="progress-bar">
              <div class="progress-fill" style="width: ${percentage}%"></div>
            </div>
          </div>
        `;
      });
      
      html += `
          </div>
          
          <div class="grid-2">
            <div class="card">
              <div class="card-header">
                <div class="card-icon">📋</div>
                <div class="card-title">Data Summary</div>
              </div>
              <div class="card-text">
      `;
      
      sortedTypes.forEach(type => {
        html += `<p><strong>${getTypeIcon(type)} ${type.charAt(0).toUpperCase() + type.slice(1)}s:</strong> ${breakdown[type]} records</p>`;
      });
      
      html += `
              </div>
            </div>
            
            <div class="card">
              <div class="card-header">
                <div class="card-icon">💡</div>
                <div class="card-title">Data Management Tips</div>
              </div>
              <div class="card-text">
                <p>📊 Export data regularly for backup</p>
                <p>🗑️ Delete unused records to free space</p>
                <p>📈 Monitor storage usage in Analytics</p>
                <p>⚠️ Warning appears at 999 records</p>
                <p>🔍 Use filters to find specific data</p>
              </div>
            </div>
          </div>
          
          <div class="data-section" style="margin-top: 25px;">
            <h3 style="font-size: 18px; font-weight: 900; margin-bottom: 15px; color: #1f2937; display: flex; align-items: center; gap: 10px;">
              <span style="font-size: 24px;">🔧</span>
              <span>Data Actions</span>
            </h3>
            <div style="display: flex; gap: 12px; flex-wrap: wrap;">
              <button class="btn btn-success" onclick="exportAllData()">
                <span>📊</span><span>Export All Data (CSV)</span>
              </button>
              <button class="btn btn-primary" onclick="renderAnalytics()">
                <span>📈</span><span>View Analytics</span>
              </button>
              <button class="btn btn-secondary" onclick="renderDashboard()">
                <span>🏠</span><span>Go to Dashboard</span>
              </button>
            </div>
          </div>
        </div>
      `;
      
      document.getElementById('contentArea').innerHTML = html;
    }
    
    initApp();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9a6730a694804992',t:'MTc2NDQ3MjYyOC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
