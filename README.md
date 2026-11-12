<!doctype html>
<html lang="ru">
	<head>
		<meta charset="utf-8" />
		<link
			rel="icon"
			type="image/svg+xml"
			href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><rect width='100' height='100' rx='20' fill='%230f172a'/><path d='M25 25 L50 85 L75 25 L58 25 L50 52 L42 25 Z' fill='%23f43f5e'/></svg>"
		/>
		<title>[NEXUS] // VALORANT_STORE</title>
		<meta
			name="viewport"
			content="width=device-width, initial-scale=1, user-scalable=no, viewport-fit=cover"
		/>
		<script>
			try {
				var __t = localStorage.getItem('nexus-theme');
				if (__t) document.documentElement.setAttribute('data-theme', __t);
				var __r = localStorage.getItem('nexus-val-region');
				if (__r) window.__valRegion = __r;
			} catch (e) {}
		</script>
		<link rel="preconnect" href="https://fonts.googleapis.com" />
		<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
		<link
			href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;900&family=Roboto+Mono:wght@400;500;700&display=swap"
			rel="stylesheet"
		/>
		<style>
			:root {
				--accent-rgb: 56, 189, 248;
				--accent: #38bdf8;
				--accent-2-rgb: 167, 139, 250;
				--accent-glow: rgba(var(--accent-rgb), 0.25);
				--bg-base: #050a18;
				--card-bg: linear-gradient(
					135deg,
					rgba(21, 27, 43, 0.6) 0%,
					rgba(13, 17, 28, 0.5) 100%
				);
				--card-hover-bg: rgba(30, 41, 59, 0.55);
				--text: #f8fafc;
				--dim: #94a3b8;
				--border: rgba(255, 255, 255, 0.08);
				--border-strong: rgba(255, 255, 255, 0.14);
				--ok: 34, 197, 94;
				--warn: 251, 191, 36;
				--err: 244, 63, 94;
			}
			html[data-theme='emerald'] {
				--accent-rgb: 16, 185, 129;
				--accent: #10b981;
				--accent-2-rgb: 6, 182, 212;
				--bg-base: #030806;
			}
			html[data-theme='amber'] {
				--accent-rgb: 245, 158, 11;
				--accent: #f59e0b;
				--accent-2-rgb: 239, 68, 68;
				--bg-base: #0a0703;
			}
			html[data-theme='crimson'] {
				--accent-rgb: 244, 63, 94;
				--accent: #f43f5e;
				--accent-2-rgb: 249, 115, 22;
				--bg-base: #0a0407;
			}
			html[data-theme='violet'] {
				--accent-rgb: 167, 139, 250;
				--accent: #a78bfa;
				--accent-2-rgb: 236, 72, 153;
				--bg-base: #07040d;
			}
			html[data-theme='mono'] {
				--accent-rgb: 203, 213, 225;
				--accent: #cbd5e1;
				--accent-2-rgb: 100, 116, 139;
				--bg-base: #06080c;
			}

			* {
				box-sizing: border-box;
				-webkit-tap-highlight-color: transparent;
			}
			html,
			body {
				height: 100%;
			}

			body {
				background:
					radial-gradient(
						circle at 12% 0%,
						rgba(var(--accent-rgb), 0.09) 0%,
						transparent 42%
					),
					radial-gradient(
						circle at 88% 100%,
						rgba(var(--accent-2-rgb), 0.07) 0%,
						transparent 45%
					),
					var(--bg-base);
				background-attachment: fixed;
				color: var(--text);
				font-family: 'Inter', sans-serif;
				margin: 0;
				min-height: 100vh;
				display: flex;
				flex-direction: column;
				align-items: center;
				overflow-x: hidden;
				padding: 96px 20px 60px;
				animation: pageIn 0.8s cubic-bezier(0.16, 1, 0.3, 1);
			}
			@keyframes pageIn {
				from {
					opacity: 0;
					transform: translateY(12px);
				}
				to {
					opacity: 1;
					transform: none;
				}
			}

			#canvas-plexus {
				position: fixed;
				inset: 0;
				z-index: 0;
				pointer-events: none;
			}

			/* ============ HEADER ============ */
			.header {
				position: fixed;
				top: 0;
				left: 0;
				width: 100%;
				height: 68px;
				background: rgba(15, 23, 42, 0.45);
				backdrop-filter: blur(24px) saturate(160%);
				-webkit-backdrop-filter: blur(24px) saturate(160%);
				border-bottom: 1px solid var(--border);
				display: grid;
				grid-template-columns: 1fr auto 1fr;
				align-items: center;
				padding: 0 28px;
				z-index: 1000;
			}
			.back-btn {
				justify-self: start;
				text-decoration: none;
				color: var(--text);
				font-size: 11px;
				font-family: 'Roboto Mono', monospace;
				font-weight: 500;
				border: 1px solid var(--border);
				padding: 8px 14px;
				border-radius: 10px;
				background: rgba(255, 255, 255, 0.03);
				letter-spacing: 1px;
				display: inline-flex;
				align-items: center;
				gap: 8px;
				transition: all 0.25s ease;
			}
			.back-btn:hover {
				background: rgba(var(--accent-rgb), 0.12);
				border-color: rgba(var(--accent-rgb), 0.5);
				transform: translateX(-2px);
			}
			.back-btn svg {
				width: 11px;
				height: 11px;
				fill: currentColor;
				opacity: 0.7;
			}
			.system-title {
				justify-self: center;
				font-family: 'Roboto Mono', monospace;
				font-size: 12px;
				font-weight: 600;
				color: var(--accent);
				letter-spacing: 3.5px;
				display: flex;
				align-items: center;
				gap: 10px;
				text-shadow: 0 0 20px var(--accent-glow);
				white-space: nowrap;
			}
			.system-title::before,
			.system-title::after {
				content: '';
				width: 6px;
				height: 6px;
				border-radius: 50%;
				background: var(--accent);
				box-shadow: 0 0 10px var(--accent);
				opacity: 0.75;
			}
			.conn-status {
				justify-self: end;
				display: flex;
				align-items: center;
				gap: 8px;
				font-family: 'Roboto Mono', monospace;
				font-size: 10px;
				font-weight: 600;
				letter-spacing: 1.5px;
				color: var(--dim);
				white-space: nowrap;
			}
			.conn-dot {
				width: 8px;
				height: 8px;
				border-radius: 50%;
				background: rgb(var(--err));
				box-shadow: 0 0 8px rgba(var(--err), 0.5);
				transition: all 0.3s ease;
			}
			.conn-status.online {
				color: rgb(var(--ok));
			}
			.conn-status.online .conn-dot {
				background: rgb(var(--ok));
				box-shadow: 0 0 10px rgba(var(--ok), 0.65);
				animation: pulseDot 2s ease-in-out infinite;
			}
			.conn-status.waiting {
				color: rgb(var(--warn));
			}
			.conn-status.waiting .conn-dot {
				background: rgb(var(--warn));
				box-shadow: 0 0 10px rgba(var(--warn), 0.6);
				animation: pulseDot 1s ease-in-out infinite;
			}
			@keyframes pulseDot {
				0%,
				100% {
					opacity: 1;
				}
				50% {
					opacity: 0.4;
				}
			}

			/* ============ CONTAINER ============ */
			.wrap {
				position: relative;
				z-index: 10;
				width: 100%;
				max-width: 1100px;
				display: flex;
				flex-direction: column;
				gap: 18px;
			}

			/* ============ TOOLBAR ============ */
			.toolbar {
				display: flex;
				align-items: center;
				gap: 10px;
				flex-wrap: wrap;
				background: var(--card-bg);
				backdrop-filter: blur(24px) saturate(150%);
				-webkit-backdrop-filter: blur(24px) saturate(150%);
				border: 1px solid var(--border);
				border-radius: 16px;
				padding: 10px 14px;
				position: relative;
			}
			.toolbar::before {
				content: '';
				position: absolute;
				top: 0;
				left: 15%;
				right: 15%;
				height: 1px;
				background: linear-gradient(
					90deg,
					transparent,
					rgba(var(--accent-rgb), 0.4),
					transparent
				);
				pointer-events: none;
			}
			.reg-selector {
				display: flex;
				gap: 4px;
				padding: 3px;
				background: rgba(0, 0, 0, 0.25);
				border: 1px solid var(--border);
				border-radius: 10px;
			}
			.reg-btn {
				background: transparent;
				border: none;
				cursor: pointer;
				font-family: 'Roboto Mono', monospace;
				font-size: 10px;
				font-weight: 700;
				letter-spacing: 1px;
				color: var(--dim);
				padding: 6px 12px;
				border-radius: 7px;
				transition: 0.2s;
			}
			.reg-btn:hover {
				color: var(--text);
			}
			.reg-btn.active {
				background: rgba(var(--accent-rgb), 0.16);
				color: var(--accent);
			}

			.stat-pill {
				display: inline-flex;
				align-items: center;
				gap: 8px;
				padding: 7px 14px;
				border-radius: 100px;
				border: 1px solid rgba(var(--accent-rgb), 0.3);
				background: rgba(var(--accent-rgb), 0.08);
				color: var(--accent);
				font-family: 'Roboto Mono', monospace;
				font-size: 12px;
				font-weight: 700;
				letter-spacing: 0.5px;
				white-space: nowrap;
			}
			.stat-pill svg {
				width: 14px;
				height: 14px;
				fill: currentColor;
			}
			.stat-pill.timer {
				color: rgb(var(--warn));
				border-color: rgba(var(--warn), 0.35);
				background: rgba(var(--warn), 0.08);
			}
			.stat-pill.timer svg {
				fill: rgb(var(--warn));
			}

			.tb-btn {
				margin-left: auto;
				display: inline-flex;
				align-items: center;
				gap: 6px;
				background: rgba(255, 255, 255, 0.03);
				border: 1px solid var(--border);
				color: var(--dim);
				font-family: 'Roboto Mono', monospace;
				font-size: 10px;
				font-weight: 600;
				letter-spacing: 1px;
				padding: 8px 14px;
				border-radius: 10px;
				cursor: pointer;
				transition: all 0.2s ease;
				text-transform: uppercase;
			}
			.tb-btn svg {
				width: 12px;
				height: 12px;
				fill: currentColor;
			}
			.tb-btn:hover {
				color: var(--text);
				border-color: rgba(var(--accent-rgb), 0.4);
				background: rgba(var(--accent-rgb), 0.06);
			}
			.tb-btn.spinning svg {
				animation: spin 1s linear infinite;
			}
			@keyframes spin {
				to {
					transform: rotate(360deg);
				}
			}

			/* ============ GRID ============ */
			.store-grid {
				display: grid;
				grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
				gap: 18px;
				width: 100%;
				min-height: 320px;
			}

			.skin-card {
				position: relative;
				background: var(--card-bg);
				backdrop-filter: blur(24px) saturate(140%);
				-webkit-backdrop-filter: blur(24px) saturate(140%);
				border: 1px solid var(--border);
				border-radius: 22px;
				overflow: hidden;
				display: flex;
				flex-direction: column;
				transition:
					transform 0.4s cubic-bezier(0.16, 1, 0.3, 1),
					border-color 0.3s,
					box-shadow 0.3s,
					background 0.3s;
				animation: cardIn 0.5s cubic-bezier(0.16, 1, 0.3, 1) backwards;
				min-height: 300px;
				cursor: pointer;
			}
			@keyframes cardIn {
				from {
					opacity: 0;
					transform: translateY(16px) scale(0.97);
				}
				to {
					opacity: 1;
					transform: none;
				}
			}
			.skin-card::before {
				content: '';
				position: absolute;
				top: 0;
				left: 0;
				right: 0;
				height: 3px;
				background: var(--tier-color, var(--accent));
				opacity: 0.9;
				box-shadow: 0 0 20px var(--tier-color, var(--accent));
			}
			.skin-card:hover {
				transform: translateY(-6px);
				border-color: color-mix(
					in srgb,
					var(--tier-color, var(--accent)) 55%,
					transparent
				);
				box-shadow:
					0 24px 48px -18px rgba(0, 0, 0, 0.85),
					0 0 36px -8px
						color-mix(
							in srgb,
							var(--tier-color, var(--accent)) 60%,
							transparent
						);
				background: var(--card-hover-bg);
			}

			.skin-img-wrap {
				position: relative;
				width: 100%;
				aspect-ratio: 16/10;
				background: linear-gradient(
					135deg,
					rgba(0, 0, 0, 0.4),
					rgba(0, 0, 0, 0.15)
				);
				display: flex;
				align-items: center;
				justify-content: center;
				overflow: hidden;
			}
			.skin-img-wrap::after {
				content: '';
				position: absolute;
				inset: 0;
				background: linear-gradient(
					to bottom,
					transparent 50%,
					rgba(0, 0, 0, 0.7) 100%
				);
				pointer-events: none;
			}
			.skin-img {
				width: 85%;
				height: 85%;
				object-fit: contain;
				filter: drop-shadow(0 10px 24px rgba(0, 0, 0, 0.6));
				transition: transform 0.5s cubic-bezier(0.16, 1, 0.3, 1);
			}
			.skin-card:hover .skin-img {
				transform: scale(1.08) translateY(-2px);
			}

			.skin-body {
				padding: 16px 18px 18px;
				display: flex;
				flex-direction: column;
				gap: 10px;
				flex: 1;
			}
			.tier-badge {
				display: inline-flex;
				align-items: center;
				gap: 6px;
				align-self: flex-start;
				font-family: 'Roboto Mono', monospace;
				font-size: 9px;
				font-weight: 700;
				letter-spacing: 1.5px;
				text-transform: uppercase;
				padding: 3px 9px;
				border-radius: 100px;
				color: var(--tier-color, var(--accent));
				border: 1px solid
					color-mix(in srgb, var(--tier-color, var(--accent)) 45%, transparent);
				background: color-mix(
					in srgb,
					var(--tier-color, var(--accent)) 12%,
					transparent
				);
			}
			.skin-name {
				font-size: 16px;
				font-weight: 700;
				color: var(--text);
				letter-spacing: -0.2px;
				line-height: 1.3;
				margin: 0;
				min-height: 42px;
			}
			.skin-price {
				display: inline-flex;
				align-items: center;
				gap: 6px;
				align-self: flex-start;
				margin-top: auto;
				padding: 7px 14px;
				border-radius: 10px;
				background: rgba(var(--accent-rgb), 0.12);
				border: 1px solid rgba(var(--accent-rgb), 0.35);
				color: var(--accent);
				font-family: 'Roboto Mono', monospace;
				font-size: 13px;
				font-weight: 700;
				letter-spacing: 0.3px;
			}
			.skin-price svg {
				width: 14px;
				height: 14px;
				fill: currentColor;
			}

			.skin-skeleton {
				background: var(--card-bg);
				border: 1px solid var(--border);
				border-radius: 22px;
				overflow: hidden;
				min-height: 300px;
				position: relative;
			}
			.skin-skeleton::before {
				content: '';
				position: absolute;
				inset: 0;
				background: linear-gradient(
					90deg,
					transparent,
					rgba(255, 255, 255, 0.04),
					transparent
				);
				background-size: 200% 100%;
				animation: shimmer 1.5s infinite;
			}
			@keyframes shimmer {
				0% {
					background-position: 200% 0;
				}
				100% {
					background-position: -200% 0;
				}
			}

			/* ============ EMPTY / ERROR ============ */
			.state-box {
				grid-column: 1 / -1;
				display: flex;
				flex-direction: column;
				align-items: center;
				gap: 16px;
				padding: 60px 20px;
				text-align: center;
				font-family: 'Roboto Mono', monospace;
				animation: cardIn 0.5s cubic-bezier(0.16, 1, 0.3, 1);
				background: var(--card-bg);
				border: 1px dashed var(--border);
				border-radius: 22px;
			}
			.state-icon {
				width: 84px;
				height: 84px;
				border-radius: 50%;
				background: radial-gradient(
					circle,
					rgba(var(--accent-rgb), 0.1) 0%,
					transparent 70%
				);
				display: flex;
				align-items: center;
				justify-content: center;
				position: relative;
			}
			.state-icon svg {
				width: 40px;
				height: 40px;
				fill: var(--accent);
				opacity: 0.55;
			}
			.state-icon::before,
			.state-icon::after {
				content: '';
				position: absolute;
				inset: 12px;
				border-radius: 50%;
				border: 1px solid rgba(var(--accent-rgb), 0.35);
				animation: pulse 2.8s ease-out infinite;
			}
			.state-icon::after {
				animation-delay: 1.4s;
			}
			@keyframes pulse {
				0% {
					transform: scale(0.7);
					opacity: 0;
				}
				30% {
					opacity: 0.8;
				}
				100% {
					transform: scale(1.5);
					opacity: 0;
				}
			}
			.state-icon.err {
				background: radial-gradient(
					circle,
					rgba(var(--err), 0.1) 0%,
					transparent 70%
				);
			}
			.state-icon.err svg {
				fill: rgb(var(--err));
			}
			.state-icon.err::before,
			.state-icon.err::after {
				border-color: rgba(var(--err), 0.35);
			}
			.state-title {
				font-size: 13px;
				font-weight: 700;
				letter-spacing: 2px;
				color: var(--text);
			}
			.state-sub {
				font-size: 11px;
				color: var(--dim);
				max-width: 360px;
				line-height: 1.6;
				letter-spacing: 0.5px;
			}
			.state-retry {
				font-size: 10px;
				color: rgb(var(--warn));
				letter-spacing: 1.5px;
				font-weight: bold;
			}

			/* ============ FOOTER BAR ============ */
			.footer-bar {
				display: flex;
				align-items: center;
				gap: 12px;
				flex-wrap: wrap;
				padding: 12px 18px;
				border-radius: 14px;
				background: var(--card-bg);
				border: 1px solid var(--border);
				backdrop-filter: blur(20px) saturate(140%);
				font-family: 'Roboto Mono', monospace;
				font-size: 10px;
				color: var(--dim);
				letter-spacing: 0.8px;
			}
			.footer-dot {
				width: 6px;
				height: 6px;
				border-radius: 50%;
				background: rgb(var(--ok));
				box-shadow: 0 0 6px rgba(var(--ok), 0.6);
				animation: pulseDot 2s ease-in-out infinite;
			}
			.footer-dot.waiting {
				background: rgb(var(--warn));
				box-shadow: 0 0 6px rgba(var(--warn), 0.6);
			}
			.footer-dot.err {
				background: rgb(var(--err));
				box-shadow: 0 0 6px rgba(var(--err), 0.6);
				animation: none;
			}
			.footer-bar b {
				color: var(--accent);
				font-weight: 700;
			}
			.footer-bar .spacer {
				flex: 1;
			}

			/* ============ GLOBAL TOOLTIP ============ */
			#global-tooltip {
				position: fixed;
				z-index: 9999;
				background: linear-gradient(
					135deg,
					rgba(15, 23, 42, 0.98) 0%,
					rgba(8, 12, 22, 0.98) 100%
				);
				backdrop-filter: blur(10px);
				-webkit-backdrop-filter: blur(10px);
				color: var(--text);
				font-family: 'Roboto Mono', monospace;
				font-size: 10px;
				font-weight: 500;
				padding: 6px 12px;
				border-radius: 6px;
				border: 1px solid rgba(var(--accent-rgb), 0.3);
				box-shadow:
					0 10px 25px -5px rgba(0, 0, 0, 0.8),
					0 0 15px rgba(var(--accent-rgb), 0.1);
				white-space: nowrap;
				opacity: 0;
				pointer-events: none;
				transform: translate(-50%, -100%) translateY(4px);
				transition:
					opacity 0.2s ease,
					transform 0.2s ease;
			}
			#global-tooltip.visible {
				opacity: 1;
				transform: translate(-50%, -100%) translateY(0);
			}

			/* ============ MODAL PREVIEW ============ */
			#skin-modal {
				position: fixed;
				inset: 0;
				z-index: 9000;
				background: rgba(4, 6, 10, 0.85);
				backdrop-filter: blur(15px);
				-webkit-backdrop-filter: blur(15px);
				display: flex;
				justify-content: center;
				align-items: center;
				opacity: 0;
				pointer-events: none;
				transition: opacity 0.3s ease;
			}
			#skin-modal.active {
				opacity: 1;
				pointer-events: auto;
			}
			.modal-close-btn {
				position: absolute;
				top: 24px;
				right: 24px;
				z-index: 10;
				width: 44px;
				height: 44px;
				border-radius: 50%;
				background: rgba(255, 255, 255, 0.06);
				border: 1px solid var(--border);
				color: var(--text);
				font-size: 20px;
				font-family: 'Roboto Mono', monospace;
				cursor: pointer;
				display: flex;
				align-items: center;
				justify-content: center;
				transition: 0.25s;
				padding: 0;
				line-height: 1;
			}
			.modal-close-btn:hover {
				background: rgba(var(--err), 0.15);
				border-color: rgba(var(--err), 0.5);
				color: rgb(var(--err));
				transform: rotate(90deg);
			}
			.modal-zoom-wrap {
				position: relative;
				width: 100%;
				height: 100%;
				display: flex;
				justify-content: center;
				align-items: center;
				overflow: hidden;
				cursor: grab;
			}
			.modal-zoom-wrap:active {
				cursor: grabbing;
			}
			.modal-img {
				max-width: 90vw;
				max-height: 85vh;
				object-fit: contain;
				transform-origin: center center;
				transition: transform 0.1s ease-out;
				filter: drop-shadow(0 20px 40px rgba(0, 0, 0, 0.8));
				pointer-events: none;
			}
			.modal-info {
				position: absolute;
				bottom: 30px;
				left: 50%;
				transform: translateX(-50%);
				background: var(--card-bg);
				backdrop-filter: blur(20px);
				border: 1px solid var(--border);
				border-radius: 16px;
				padding: 12px 24px;
				text-align: center;
				font-family: 'Roboto Mono', monospace;
				box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
				pointer-events: none;
				display: flex;
				flex-direction: column;
				gap: 4px;
			}
			.modal-info-title {
				color: var(--text);
				font-size: 16px;
				font-weight: bold;
			}
			.modal-info-price {
				color: var(--accent);
				font-size: 14px;
			}

			/* ============ TOAST ============ */
			.toast-msg {
				position: fixed;
				bottom: 30px;
				left: 50%;
				transform: translateX(-50%) translateY(20px);
				background: #0f172a;
				border: 1px solid rgba(var(--accent-rgb), 0.55);
				color: var(--accent);
				padding: 10px 22px;
				border-radius: 40px;
				font-size: 11px;
				font-family: 'Roboto Mono', monospace;
				z-index: 10000;
				backdrop-filter: blur(10px);
				pointer-events: none;
				opacity: 0;
				transition:
					opacity 0.3s,
					transform 0.3s;
				white-space: nowrap;
				letter-spacing: 1px;
				box-shadow: 0 8px 30px -6px rgba(var(--accent-rgb), 0.4);
				max-width: calc(100vw - 32px);
				overflow: hidden;
				text-overflow: ellipsis;
			}
			.toast-msg.visible {
				opacity: 1;
				transform: translateX(-50%) translateY(0);
			}

			/* ============ CONTEXT MENU ============ */
			.ctx-menu {
				position: fixed;
				z-index: 8000;
				min-width: 240px;
				max-width: 320px;
				background: linear-gradient(
					135deg,
					rgba(15, 23, 42, 0.98),
					rgba(8, 12, 22, 0.98)
				);
				backdrop-filter: blur(20px) saturate(180%);
				border: 1px solid rgba(var(--accent-rgb), 0.25);
				border-radius: 12px;
				padding: 6px;
				box-shadow: 0 20px 50px -10px rgba(0, 0, 0, 0.85);
				opacity: 0;
				transform: scale(0.95) translateY(-4px);
				transform-origin: top left;
				pointer-events: none;
				transition:
					opacity 0.15s,
					transform 0.15s;
				max-height: 85vh;
				overflow-y: auto;
			}
			.ctx-menu.visible {
				opacity: 1;
				transform: scale(1) translateY(0);
				pointer-events: auto;
			}
			.ctx-item {
				display: flex;
				align-items: center;
				gap: 10px;
				padding: 8px 12px;
				border-radius: 8px;
				color: var(--text);
				font-size: 12px;
				cursor: pointer;
				border: none;
				background: transparent;
				width: 100%;
				text-align: left;
				white-space: nowrap;
				transition:
					background 0.12s,
					color 0.12s;
			}
			.ctx-item:hover,
			.ctx-item.ctx-highlighted {
				background: rgba(var(--accent-rgb), 0.14);
				color: var(--accent);
			}
			.ctx-item.disabled {
				opacity: 0.35;
				pointer-events: none;
			}
			.ctx-item.checked {
				color: var(--accent);
			}
			.ctx-sep {
				height: 1px;
				margin: 4px 8px;
				background: rgba(255, 255, 255, 0.06);
			}
			.ctx-header {
				padding: 10px 12px 4px;
				font-family: 'Roboto Mono', monospace;
				font-size: 9px;
				letter-spacing: 1.8px;
				text-transform: uppercase;
				color: var(--dim);
				opacity: 0.75;
				user-select: none;
			}
			.ctx-shortcut {
				margin-left: auto;
				font-family: 'Roboto Mono', monospace;
				font-size: 9px;
				color: var(--dim);
				padding: 1px 5px;
				background: rgba(255, 255, 255, 0.04);
				border: 1px solid var(--border);
				border-radius: 4px;
			}
			.ctx-dot {
				width: 12px;
				height: 12px;
				border-radius: 50%;
				flex-shrink: 0;
				box-shadow: 0 0 6px currentColor;
			}
			.ctx-check {
				width: 14px;
				text-align: center;
				font-size: 12px;
				color: var(--accent);
				opacity: 0;
			}
			.ctx-item.checked .ctx-check {
				opacity: 1;
			}

			/* ============ RESPONSIVE ============ */
			@media (max-width: 900px) {
				body {
					padding: 88px 14px 40px;
				}
				.header {
					padding: 0 18px;
				}
				.store-grid {
					grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
					gap: 14px;
				}
			}
			@media (max-width: 700px) {
				body {
					padding: 80px 10px 30px;
				}
				.header {
					height: 60px;
					padding: 0 12px;
				}
				.system-title {
					font-size: 10px;
					letter-spacing: 2px;
				}
				.system-title::before,
				.system-title::after {
					display: none;
				}
				.store-grid {
					grid-template-columns: 1fr;
				}
				.toolbar {
					padding: 8px 10px;
					gap: 8px;
				}
				.tb-btn {
					font-size: 9px;
					padding: 7px 10px;
				}
				.reg-btn {
					padding: 5px 8px;
					font-size: 9px;
				}
				.stat-pill {
					font-size: 11px;
					padding: 6px 10px;
				}
				.ctx-menu {
					left: 8px !important;
					right: 8px !important;
					bottom: 8px !important;
					top: auto !important;
					width: auto !important;
					max-width: none;
					min-width: 0;
					border-radius: 16px;
					transform-origin: bottom center;
					transform: translateY(20px) scale(0.96);
					max-height: 72vh;
				}
				.ctx-menu.visible {
					transform: translateY(0) scale(1);
				}
				.ctx-shortcut {
					display: none;
				}
				.toast-msg {
					bottom: 100px;
					left: 12px;
					right: 12px;
					max-width: none;
					white-space: normal;
					text-align: center;
				}
				#global-tooltip {
					display: none !important;
				}
				.modal-info {
					bottom: 15px;
					padding: 8px 16px;
					width: 90%;
				}
				.modal-info-title {
					font-size: 14px;
				}
				.modal-close-btn {
					top: 16px;
					right: 16px;
					width: 36px;
					height: 36px;
				}
			}
		</style>
	</head>
	<body>
		<canvas id="canvas-plexus"></canvas>

		<header class="header">
			<a href="/" class="back-btn">
				<svg viewBox="0 0 24 24">
					<path
						d="M20 11H7.83l5.59-5.59L12 4l-8 8 8 8 1.41-1.41L7.83 13H20v-2z"
					/>
				</svg>
				RETURN
			</a>
			<div class="system-title">NEXUS // VALORANT_STORE</div>
			<div class="conn-status" id="connStatus">
				<span class="conn-dot"></span>
				<span class="conn-text">CONNECTING</span>
			</div>
		</header>

		<div class="wrap">
			<div class="toolbar">
				<div
					class="reg-selector"
					id="regSelector"
					data-tooltip="Выбор региона аккаунта Riot"
				>
					<button class="reg-btn" data-reg="eu">EU</button>
					<button class="reg-btn" data-reg="na">NA</button>
					<button class="reg-btn" data-reg="ap">AP</button>
					<button class="reg-btn" data-reg="kr">KR</button>
				</div>

				<div class="stat-pill" id="vpPill" data-tooltip="Баланс очков Valorant">
					<svg viewBox="0 0 24 24">
						<path
							d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-3 6h2.5l1.5 4 1.5-4H17l-3 8h-2l-3-8z"
						/>
					</svg>
					<span id="vpVal">— VP</span>
				</div>

				<div
					class="stat-pill timer"
					id="timerPill"
					data-tooltip="Время до обновления ежедневного магазина"
				>
					<svg viewBox="0 0 24 24">
						<path
							d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm.5-13H11v6l5.25 3.15.75-1.23-4.5-2.67z"
						/>
					</svg>
					<span id="timerVal">--:--:--</span>
				</div>

				<button
					class="tb-btn"
					id="refreshBtn"
					data-tooltip="Обновить сейчас (R)"
				>
					<svg viewBox="0 0 24 24">
						<path
							d="M17.65 6.35A7.958 7.958 0 0 0 12 4a8 8 0 1 0 7.73 10h-2.08A6 6 0 1 1 12 6c1.66 0 3.14.69 4.22 1.78L13 11h7V4l-2.35 2.35z"
						/>
					</svg>
					REFRESH
				</button>
			</div>

			<div class="store-grid" id="storeGrid">
				<div class="skin-skeleton"></div>
				<div class="skin-skeleton"></div>
				<div class="skin-skeleton"></div>
				<div class="skin-skeleton"></div>
			</div>

			<div class="footer-bar">
				<span class="footer-dot" id="ftDot"></span>
				<span id="ftStatus">инициализация...</span>
				<span class="spacer"></span>
				<span>auto-refresh: <b id="autoRefreshState">60s</b></span>
			</div>
		</div>

		<!-- Модальное окно предпросмотра -->
		<div id="skin-modal">
			<button class="modal-close-btn" id="modalCloseBtn" aria-label="Закрыть">
				✕
			</button>
			<div class="modal-zoom-wrap" id="modalZoomWrap">
				<img
					class="modal-img"
					id="modalImg"
					src=""
					alt="Skin Preview"
					draggable="false"
				/>
			</div>
			<div class="modal-info" id="modalInfo">
				<div class="modal-info-title" id="modalTitle"></div>
				<div class="modal-info-price" id="modalPrice"></div>
			</div>
		</div>

		<div id="global-tooltip"></div>
		<div class="toast-msg" id="toast">✓ DONE</div>
		<div class="ctx-menu" id="ctx-menu"></div>

		<script>
			// ==========================================
			// 1. СИСТЕМА ТЕМ
			// ==========================================
			const THEMES = [
				{ id: 'nexus', label: 'Nexus', dot: '#38bdf8' },
				{ id: 'emerald', label: 'Emerald', dot: '#10b981' },
				{ id: 'amber', label: 'Amber', dot: '#f59e0b' },
				{ id: 'crimson', label: 'Crimson', dot: '#f43f5e' },
				{ id: 'violet', label: 'Violet', dot: '#a78bfa' },
				{ id: 'mono', label: 'Mono', dot: '#cbd5e1' },
			];
			const THEME_IDS = THEMES.map((t) => t.id);

			let currentTheme = 'nexus';
			try {
				const saved = localStorage.getItem('nexus-theme');
				if (saved && THEME_IDS.includes(saved)) currentTheme = saved;
			} catch (e) {}
			document.documentElement.setAttribute('data-theme', currentTheme);

			let accentRgb = '56, 189, 248';
			function updateAccentRgb() {
				const v = getComputedStyle(document.documentElement)
					.getPropertyValue('--accent-rgb')
					.trim();
				if (v) accentRgb = v;
			}
			updateAccentRgb();

			function setTheme(id) {
				if (!THEME_IDS.includes(id)) return;
				currentTheme = id;
				document.documentElement.setAttribute('data-theme', id);
				try {
					localStorage.setItem('nexus-theme', id);
				} catch (e) {}
				updateAccentRgb();
			}

			// ==========================================
			// 2. ГЛОБАЛЬНЫЕ ТУЛТИПЫ
			// ==========================================
			const globalTooltip = document.getElementById('global-tooltip');

			document.addEventListener('mouseover', (e) => {
				const target = e.target.closest('[data-tooltip]');
				if (!target) return;

				const text = target.getAttribute('data-tooltip');
				if (!text) return;

				globalTooltip.textContent = text;
				globalTooltip.classList.add('visible');

				const rect = target.getBoundingClientRect();
				const top = rect.top - 8;
				let left = rect.left + rect.width / 2;

				const tooltipRect = globalTooltip.getBoundingClientRect();

				if (left - tooltipRect.width / 2 < 10) {
					left = tooltipRect.width / 2 + 10;
				} else if (left + tooltipRect.width / 2 > window.innerWidth - 10) {
					left = window.innerWidth - tooltipRect.width / 2 - 10;
				}

				globalTooltip.style.left = `${left}px`;
				globalTooltip.style.top = `${top}px`;
			});

			document.addEventListener('mouseout', (e) => {
				if (e.target.closest('[data-tooltip]')) {
					globalTooltip.classList.remove('visible');
				}
			});

			// ==========================================
			// 3. МОДАЛЬНОЕ ОКНО (ЗУМ И ПЕРЕТАСКИВАНИЕ)
			// ==========================================
			const modal = document.getElementById('skin-modal');
			const modalImg = document.getElementById('modalImg');
			const modalTitle = document.getElementById('modalTitle');
			const modalPrice = document.getElementById('modalPrice');
			const modalZoomWrap = document.getElementById('modalZoomWrap');

			let scale = 1;
			let translateX = 0;
			let translateY = 0;
			let isDragging = false;
			let startX, startY;

			function updateTransform() {
				modalImg.style.transform = `translate(${translateX}px, ${translateY}px) scale(${scale})`;
			}

			function resetModal() {
				scale = 1;
				translateX = 0;
				translateY = 0;
				updateTransform();
			}

			function openModal(src, title, price) {
				if (!src) return;
				resetModal();
				modalImg.src = src;
				modalTitle.textContent = title;
				modalPrice.textContent = price + ' VP';
				modal.classList.add('active');
			}

			function closeModal() {
				modal.classList.remove('active');
			}

			document
				.getElementById('modalCloseBtn')
				.addEventListener('click', closeModal);
			modal.addEventListener('click', (e) => {
				if (e.target === modal || e.target === modalZoomWrap) closeModal();
			});

			// Зум колесиком
			modalZoomWrap.addEventListener(
				'wheel',
				(e) => {
					e.preventDefault();
					const delta = e.deltaY > 0 ? -0.15 : 0.15;
					scale = Math.max(0.5, Math.min(scale + delta, 5));
					updateTransform();
				},
				{ passive: false },
			);

			// Перетаскивание
			modalZoomWrap.addEventListener('pointerdown', (e) => {
				isDragging = true;
				startX = e.clientX - translateX;
				startY = e.clientY - translateY;
				modalZoomWrap.setPointerCapture(e.pointerId);
			});

			modalZoomWrap.addEventListener('pointermove', (e) => {
				if (!isDragging) return;
				translateX = e.clientX - startX;
				translateY = e.clientY - startY;
				updateTransform();
			});

			modalZoomWrap.addEventListener('pointerup', (e) => {
				isDragging = false;
				modalZoomWrap.releasePointerCapture(e.pointerId);
			});

			// ==========================================
			// 4. ЛОГИКА МАГАЗИНА И ТАЙМЕРОВ
			// ==========================================
			const POLL_OK = 60000;
			const POLL_ERR = 8000;
			let currentRegion = (window.__valRegion || 'eu').toLowerCase();
			let isFetching = false;
			let lastFetchOk = false;

			let pollTimer = null;
			let pollCountdown = 0;

			let storeSecondsLeft = 0;
			let storeTimerTick = null;

			let abortController = null;

			const $ = (id) => document.getElementById(id);
			const storeGrid = $('storeGrid');
			const connStatus = $('connStatus');
			const connText = connStatus.querySelector('.conn-text');
			const vpVal = $('vpVal');
			const timerVal = $('timerVal');
			const refreshBtn = $('refreshBtn');
			const toast = $('toast');
			const ctxMenu = $('ctx-menu');
			const ftDot = $('ftDot');
			const ftStatus = $('ftStatus');
			const autoRefreshState = $('autoRefreshState');
			const regSelector = $('regSelector');

			function showToast(text) {
				toast.textContent = text;
				toast.style.borderColor = `rgba(${accentRgb}, 0.55)`;
				toast.style.color = `rgb(${accentRgb})`;
				toast.style.boxShadow = `0 8px 30px -6px rgba(${accentRgb}, 0.4)`;
				toast.classList.add('visible');
				clearTimeout(showToast._t);
				showToast._t = setTimeout(
					() => toast.classList.remove('visible'),
					1900,
				);
			}

			function escapeHtml(s) {
				return String(s).replace(
					/[&<>"']/g,
					(c) =>
						({
							'&': '&amp;',
							'<': '&lt;',
							'>': '&gt;',
							'"': '&quot;',
							"'": '&#39;',
						})[c],
				);
			}

			function fmtTime(sec) {
				if (!sec || sec < 0) sec = 0;
				const h = Math.floor(sec / 3600);
				const m = Math.floor((sec % 3600) / 60);
				const s = sec % 60;
				return `${String(h).padStart(2, '0')}:${String(m).padStart(2, '0')}:${String(s).padStart(2, '0')}`;
			}

			function fmtVP(n) {
				return Number(n || 0).toLocaleString('ru-RU') + ' VP';
			}

			function syncRegionUI() {
				regSelector.querySelectorAll('.reg-btn').forEach((b) => {
					b.classList.toggle('active', b.dataset.reg === currentRegion);
				});
			}
			regSelector.addEventListener('click', (e) => {
				const btn = e.target.closest('.reg-btn');
				if (!btn || btn.dataset.reg === currentRegion) return;
				currentRegion = btn.dataset.reg;
				try {
					localStorage.setItem('nexus-val-region', currentRegion);
				} catch (e) {}
				syncRegionUI();
				showToast(`🌐 ${currentRegion.toUpperCase()}`);
				fetchStore(true);
			});

			function setConnState(state) {
				connStatus.classList.remove('online', 'waiting');
				if (state === 'online') {
					connStatus.classList.add('online');
					connText.textContent = 'ONLINE';
					ftDot.className = 'footer-dot';
				} else if (state === 'waiting') {
					connStatus.classList.add('waiting');
					connText.textContent = 'WAITING';
					ftDot.className = 'footer-dot waiting';
				} else {
					connText.textContent = 'OFFLINE';
					ftDot.className = 'footer-dot err';
				}
			}

			function renderStore(data) {
				vpVal.textContent = fmtVP(data.vp_balance);
				storeSecondsLeft = Math.max(0, data.time_left || 0);

				const offers = Array.isArray(data.offers) ? data.offers : [];
				if (offers.length === 0) {
					storeGrid.innerHTML = `
      <div class="state-box">
        <div class="state-icon"><svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 15h-2v-2h2v2zm0-4h-2V7h2v6z"/></svg></div>
        <div class="state-title">МАГАЗИН ПУСТ</div>
        <div class="state-sub">Riot вернул пустой список предложений</div>
      </div>`;
					return;
				}

				storeGrid.innerHTML = offers
					.map((o, i) => {
						const tier = o.tier || {};
						const tierColor = tier.color || 'var(--accent)';
						const tierLabel = tier.label || tier.name || 'SKIN';

						// Прямая ссылка на CDN (без прокси)
						const iconUrl = o.icon || '';
						const imgHtml = iconUrl
							? `<img class="skin-img" src="${iconUrl}" alt="" loading="lazy" onerror="this.style.opacity=0.2">`
							: '<div style="width:60%;height:60%;border:1px dashed var(--border);border-radius:8px;"></div>';

						return `
      <div class="skin-card" data-img="${iconUrl}" data-name="${escapeHtml(o.name || 'Unknown')}" data-price="${o.cost || 0}" style="--tier-color:${tierColor}; animation-delay: ${i * 60}ms">
        <div class="skin-img-wrap">${imgHtml}</div>
        <div class="skin-body">
          <span class="tier-badge">${escapeHtml(tierLabel)}</span>
          <h3 class="skin-name">${escapeHtml(o.name || 'Unknown')}</h3>
          <div class="skin-price">
            <svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-3 6h2.5l1.5 4 1.5-4H17l-3 8h-2l-3-8z"/></svg>
            ${Number(o.cost || 0).toLocaleString('ru-RU')} VP
          </div>
        </div>
      </div>`;
					})
					.join('');
			}

			// Делегирование клика для открытия модалки
			storeGrid.addEventListener('click', (e) => {
				const card = e.target.closest('.skin-card');
				if (!card) return;
				const src = card.dataset.img;
				const name = card.dataset.name;
				const price = card.dataset.price;
				openModal(src, name, price);
			});

			function renderErrorState(err) {
				const code = (err && err.code) || 'UNKNOWN';
				const msg = (err && err.error) || 'Неизвестная ошибка';
				const isSoft =
					code === 'CLIENT_OFFLINE' ||
					code === 'NETWORK' ||
					code === 'AUTH_FAILED';

				if (isSoft) {
					setConnState('waiting');
					ftStatus.textContent = 'ожидание Riot Client...';
					storeGrid.innerHTML = `
      <div class="state-box">
        <div class="state-icon"><svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 15h-2v-2h2v2zm0-4h-2V7h2v6z"/></svg></div>
        <div class="state-title">RIOT CLIENT НЕ НАЙДЕН</div>
        <div class="state-sub">${escapeHtml(msg)}<br>Запустите Riot Client и магазин подгрузится автоматически</div>
        <div class="state-retry">повтор через <span id="errRetryCount">${POLL_ERR / 1000}</span>с</div>
      </div>`;
					return;
				}

				setConnState('offline');
				ftStatus.textContent = msg.slice(0, 48);
				storeGrid.innerHTML = `
    <div class="state-box">
      <div class="state-icon err"><svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 15h-2v-2h2v2zm0-4h-2V7h2v6z"/></svg></div>
      <div class="state-title">ОШИБКА: ${escapeHtml(code)}</div>
      <div class="state-sub">${escapeHtml(msg)}</div>
      <div class="state-retry">повтор через <span id="errRetryCount">${POLL_ERR / 1000}</span>с</div>
    </div>`;
			}

			function startStoreTimer() {
				clearInterval(storeTimerTick);
				storeTimerTick = setInterval(() => {
					if (storeSecondsLeft > 0) {
						storeSecondsLeft--;
						timerVal.textContent = fmtTime(storeSecondsLeft);
						if (storeSecondsLeft === 0) fetchStore(true);
					} else {
						timerVal.textContent = '--:--:--';
					}
				}, 1000);
			}

			function scheduleNext(delayMs) {
				clearInterval(pollTimer);
				pollCountdown = Math.round(delayMs / 1000);
				autoRefreshState.textContent = `${pollCountdown}s`;

				pollTimer = setInterval(() => {
					pollCountdown--;
					if (pollCountdown > 0) {
						autoRefreshState.textContent = `${pollCountdown}s`;
						const errRetry = document.getElementById('errRetryCount');
						if (errRetry) errRetry.textContent = pollCountdown;
					} else {
						autoRefreshState.textContent = `0s`;
						clearInterval(pollTimer);
						fetchStore(false);
					}
				}, 1000);
			}

			async function fetchStore(force = false) {
				if (isFetching) return;
				isFetching = true;
				if (force) refreshBtn.classList.add('spinning');

				if (abortController) abortController.abort();
				abortController = new AbortController();
				const timeoutId = setTimeout(() => abortController.abort(), 12000);

				try {
					const res = await fetch(
						`/api/valorant/store?region=${encodeURIComponent(currentRegion)}`,
						{
							cache: 'no-store',
							signal: abortController.signal,
						},
					);
					clearTimeout(timeoutId);

					let data = null;
					try {
						data = await res.json();
					} catch (e) {
						data = null;
					}

					if (!res.ok || !data || data.error) {
						lastFetchOk = false;
						renderErrorState(
							data || { error: `HTTP ${res.status}`, code: 'HTTP' },
						);
						scheduleNext(POLL_ERR);
						return;
					}

					lastFetchOk = true;
					setConnState('online');
					ftStatus.textContent = `обновлено в ${new Date().toLocaleTimeString('ru-RU')}`;
					renderStore(data);
					startStoreTimer();
					timerVal.textContent = fmtTime(storeSecondsLeft);
					scheduleNext(POLL_OK);
					if (force) showToast('✓ обновлено');
				} catch (e) {
					clearTimeout(timeoutId);
					lastFetchOk = false;
					if (e.name === 'AbortError') {
						renderErrorState({
							error: 'Превышено время ожидания сервера',
							code: 'TIMEOUT',
						});
					} else {
						renderErrorState({
							error: 'Нет соединения с сервером',
							code: 'SERVER_DOWN',
						});
					}
					scheduleNext(POLL_ERR);
				} finally {
					isFetching = false;
					if (force)
						setTimeout(() => refreshBtn.classList.remove('spinning'), 500);
				}
			}

			refreshBtn.addEventListener('click', () => fetchStore(true));

			document.addEventListener('visibilitychange', () => {
				if (!document.hidden) fetchStore(true);
			});

			// ==========================================
			// 5. КОНТЕКСТНОЕ МЕНЮ
			// ==========================================
			function renderMenu(items) {
				ctxMenu.innerHTML = items
					.map((it) => {
						if (it.sep) return '<div class="ctx-sep"></div>';
						if (it.header)
							return `<div class="ctx-header">${escapeHtml(it.header)}</div>`;
						const cls = ['ctx-item'];
						if (it.disabled) cls.push('disabled');
						if (it.checked) cls.push('checked');
						const left = it.dot
							? `<span class="ctx-dot" style="background:${it.dot};color:${it.dot}"></span>`
							: it.icon || '';
						const check = `<span class="ctx-check">${it.checked ? '✓' : ''}</span>`;
						const shortcut = it.shortcut
							? `<span class="ctx-shortcut">${escapeHtml(it.shortcut)}</span>`
							: '';
						return `<button class="${cls.join(' ')}" data-action="${it.action}" data-theme="${it.themeId || ''}" data-region="${it.region || ''}">${left}<span class="ctx-label">${escapeHtml(it.label)}</span>${check}${shortcut}</button>`;
					})
					.join('');
			}

			function openCtxMenu(x, y) {
				const items = [{ header: 'Тема оформления' }];
				THEMES.forEach((t) =>
					items.push({
						action: 'set-theme',
						themeId: t.id,
						dot: t.dot,
						label: t.label,
						checked: currentTheme === t.id,
					}),
				);
				items.push({ sep: true });
				items.push({ header: 'Регион' });
				['eu', 'na', 'ap', 'kr'].forEach((r) =>
					items.push({
						action: 'set-region',
						region: r,
						icon: '<svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2z"/></svg>',
						label: r.toUpperCase(),
						checked: currentRegion === r,
					}),
				);
				items.push({ sep: true });
				items.push({
					action: 'refresh',
					icon: '<svg viewBox="0 0 24 24"><path d="M17.65 6.35A7.958 7.958 0 0 0 12 4a8 8 0 1 0 7.73 10h-2.08A6 6 0 1 1 12 6c1.66 0 3.14.69 4.22 1.78L13 11h7V4l-2.35 2.35z"/></svg>',
					label: 'Обновить сейчас',
					shortcut: 'R',
				});
				renderMenu(items);

				if (window.innerWidth <= 700) {
					ctxMenu.style.left = '';
					ctxMenu.style.top = '';
					ctxMenu.classList.add('visible');
					return;
				}

				ctxMenu.style.left = '-9999px';
				ctxMenu.style.top = '0px';
				ctxMenu.classList.add('visible');
				const rect = ctxMenu.getBoundingClientRect();
				const pad = 8;
				let px = x,
					py = y;
				if (px + rect.width > window.innerWidth - pad)
					px = Math.max(pad, x - rect.width);
				if (py + rect.height > window.innerHeight - pad)
					py = Math.max(pad, y - rect.height);
				ctxMenu.style.left = px + 'px';
				ctxMenu.style.top = py + 'px';
			}

			function closeCtxMenu() {
				ctxMenu.classList.remove('visible');
			}

			document.addEventListener('contextmenu', (e) => {
				e.preventDefault();
				if (e.target.closest('#ctx-menu')) return;
				openCtxMenu(e.clientX, e.clientY);
			});
			document.addEventListener('pointerdown', (e) => {
				if (
					ctxMenu.classList.contains('visible') &&
					!ctxMenu.contains(e.target)
				)
					closeCtxMenu();
			});
			ctxMenu.addEventListener('pointerdown', (e) => e.stopPropagation());
			window.addEventListener('resize', closeCtxMenu);
			window.addEventListener('blur', closeCtxMenu);

			ctxMenu.addEventListener('click', (e) => {
				const item = e.target.closest('.ctx-item');
				if (!item || item.classList.contains('disabled')) return;
				const action = item.dataset.action;
				if (action === 'set-theme') {
					const id = item.dataset.theme;
					setTheme(id);
					const t = THEMES.find((x) => x.id === id);
					showToast(`🎨 ${t ? t.label : id}`);
					closeCtxMenu();
					return;
				}
				if (action === 'set-region') {
					const r = item.dataset.region;
					currentRegion = r;
					try {
						localStorage.setItem('nexus-val-region', r);
					} catch (e) {}
					syncRegionUI();
					showToast(`🌐 ${r.toUpperCase()}`);
					closeCtxMenu();
					fetchStore(true);
					return;
				}
				if (action === 'refresh') {
					closeCtxMenu();
					fetchStore(true);
					return;
				}
			});

			// ==========================================
			// 6. ГОРЯЧИЕ КЛАВИШИ И PLEXUS
			// ==========================================
			document.addEventListener('keydown', (e) => {
				const tag = (e.target.tagName || '').toLowerCase();
				const inField =
					tag === 'input' || tag === 'textarea' || e.target.isContentEditable;
				if (e.key === 'Escape') {
					closeCtxMenu();
					closeModal();
					return;
				}
				if (inField) return;
				if (e.key === 'r' || e.key === 'R' || e.key === 'к' || e.key === 'К') {
					e.preventDefault();
					fetchStore(true);
				}
			});

			const canvas = document.getElementById('canvas-plexus');
			const ctx2d = canvas.getContext('2d');
			let pts = [];
			function resizeCanvas() {
				canvas.width = window.innerWidth;
				canvas.height = window.innerHeight;
			}
			window.addEventListener('resize', () => {
				resizeCanvas();
				initPlexus();
			});
			resizeCanvas();

			class Pt {
				constructor() {
					this.x = Math.random() * canvas.width;
					this.y = Math.random() * canvas.height;
					this.vx = (Math.random() - 0.5) * 0.35;
					this.vy = (Math.random() - 0.5) * 0.35;
				}
				update() {
					this.x += this.vx;
					this.y += this.vy;
					if (this.x < 0 || this.x > canvas.width) this.vx *= -1;
					if (this.y < 0 || this.y > canvas.height) this.vy *= -1;
				}
			}
			function initPlexus() {
				pts = [];
				const count = window.innerWidth < 560 ? 30 : 60;
				for (let i = 0; i < count; i++) pts.push(new Pt());
			}
			function animPlexus() {
				ctx2d.clearRect(0, 0, canvas.width, canvas.height);
				pts.forEach((p, i) => {
					p.update();
					ctx2d.fillStyle = `rgba(${accentRgb}, 0.35)`;
					ctx2d.beginPath();
					ctx2d.arc(p.x, p.y, 1.3, 0, Math.PI * 2);
					ctx2d.fill();
					for (let j = i + 1; j < pts.length; j++) {
						const d = Math.hypot(p.x - pts[j].x, p.y - pts[j].y);
						if (d < 150) {
							ctx2d.strokeStyle = `rgba(${accentRgb}, ${0.3 - d / 150})`;
							ctx2d.lineWidth = 0.75;
							ctx2d.beginPath();
							ctx2d.moveTo(p.x, p.y);
							ctx2d.lineTo(pts[j].x, pts[j].y);
							ctx2d.stroke();
						}
					}
				});
				requestAnimationFrame(animPlexus);
			}

			// Инициализация
			syncRegionUI();
			setConnState('waiting');
			ftStatus.textContent = 'запрос магазина...';
			fetchStore(true);

			window.addEventListener(
				'load',
				() => {
					initPlexus();
					animPlexus();
				},
				{ once: true },
			);
		</script>
	</body>
</html>
