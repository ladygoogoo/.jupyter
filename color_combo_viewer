
import itertools

def color_combinations(hex_codes, r):
    """
    Generates all combinations of r colors from a list of hex codes.
    """
    return list(itertools.combinations(hex_codes, r))
# --- Run as standalone script ---
if __name__ == "__main__":
    hex_codes = [
        "#DF221E", "#A52516", "#A52A2A", "#650808", "#FA775E", "#C77768",
        "#B54146", "#531320", "#FA88AA", "#FF7260", "#DF3109", "#BA3017",
        "#E20C7C", "#4D182D"
    ]
    # Set how many colors per combination
    r = 2  # Change to 3 for triplets
    # Generate color combos
    combos = color_combinations(hex_codes, r)
    print(f"Generated {len(combos)} combinations of {r} colors.")
    print("First 5 combinations:")
    for c in combos[:5]:
        print(c)
    
   

import matplotlib.pyplot as plt


def color_combinations(hex_codes, r):
    """
    Generates all combinations of r colors from a list of hex codes.
    """
    return list(itertools.combinations(hex_codes, r))


def visualize_hex_combinations(hex_combos, cols=5, save_path=None, show_labels=True):
    """
    Displays hex color combinations visually with optional hex labels.
    """
    rows = len(hex_combos)
    fig, ax = plt.subplots(figsize=(cols * 2, rows * 0.7))
    ax.set_xlim(0, cols)
    ax.set_ylim(0, rows)
    ax.set_xticks([])
    ax.set_yticks([])
    ax.set_aspect('equal')

    for row_idx, combo in enumerate(hex_combos[:rows]):
        for col_idx, hex_color in enumerate(combo):
            x = col_idx
            y = rows - 1 - row_idx

            # Draw rectangle
            rect = plt.Rectangle((x, y), 1, 1, facecolor=hex_color, edgecolor='black', linewidth=0.3)
            ax.add_patch(rect)

            # Add hex label
            if show_labels:
                ax.text(x + 0.5, y + 0.5, hex_color, color='white' if is_dark(hex_color) else 'black',
                        ha='center', va='center', fontsize=7)

    plt.tight_layout()
    if save_path:
        plt.savefig(save_path, dpi=300)
    plt.show()


def is_dark(hex_color):
    """
    Determines if a color is dark or light using luminance.
    """
    hex_color = hex_color.lstrip('#')
    r, g, b = [int(hex_color[i:i+2], 16) for i in (0, 2, 4)]
    luminance = 0.299 * r + 0.587 * g + 0.114 * b
    return luminance < 150


# --- Run as standalone script ---
if __name__ == "__main__":
    hex_codes = [
        "#DF221E", "#A52516", "#A52A2A", "#650808", "#FA775E", "#C77768",
        "#B54146", "#531320", "#FA88AA", "#FF7260", "#DF3109", "#BA3017",
        "#E20C7C", "#4D182D"
    ]

    # Set how many colors per combination
    r = 3  # Change to 3 for triplets

    # Generate color combos
    combos = color_combinations(hex_codes, r)

    print(f"Generated {len(combos)} combinations of {r} colors.")
    print("First 5 combinations:")
    for c in combos[:5]:
        print(c)


# Visualize the first 20 combinations
    visualize_hex_combinations(combos[:20], cols=r, show_labels=True, save_path=None)

# Visualize all combinations (replace the line that says "Visualize the first 20 combinations")
visualize_hex_combinations(combos, cols=r, show_labels=True, save_path=None)

import itertools
import matplotlib.pyplot as plt

def color_combinations(hex_codes, r):
    """
    Generates all combinations of r colors from a list of hex codes.
    """
    return list(itertools.combinations(hex_codes, r))

def hex_to_rgb(hex_color):
    """
    Converts hex color to RGB tuple.
    """
    hex_color = hex_color.lstrip('#')
    return tuple(int(hex_color[i:i+2], 16) for i in (0, 2, 4))

def rgb_to_hex(rgb):
    """
    Converts RGB tuple to hex color.
    """
    return '#{:02X}{:02X}{:02X}'.format(*rgb)

def mix_colors(combo):
    """
    Averages RGB values to get a blended color.
    """
    rgbs = [hex_to_rgb(c) for c in combo]
    avg_rgb = tuple(sum(channel) // len(channel) for channel in zip(*rgbs))
    return rgb_to_hex(avg_rgb)

def is_dark(hex_color):
    """
    Determines if a color is dark or light using luminance.
    """
    r, g, b = hex_to_rgb(hex_color)
    luminance = 0.299 * r + 0.587 * g + 0.114 * b
    return luminance < 150

def visualize_hex_combinations(hex_combos, cols=5, show_labels=True, save_path=None):
    """
    Displays original color combinations + their blended color.
    """
    rows = len(hex_combos)
    fig, ax = plt.subplots(figsize=(cols * 2, rows * 0.7))
    ax.set_xlim(0, cols + 1)  # +1 for mixed color
    ax.set_ylim(0, rows)
    ax.set_xticks([])
    ax.set_yticks([])
    ax.set_aspect('equal')

    for row_idx, combo in enumerate(hex_combos):
        for col_idx, hex_color in enumerate(combo):
            x = col_idx
            y = rows - 1 - row_idx
            rect = plt.Rectangle((x, y), 1, 1, facecolor=hex_color, edgecolor='black', linewidth=0.3)
            ax.add_patch(rect)
            if show_labels:
                ax.text(x + 0.5, y + 0.5, hex_color, color='white' if is_dark(hex_color) else 'black',
                        ha='center', va='center', fontsize=7)

        # Add the blended color at the end
        blended = mix_colors(combo)
        rect = plt.Rectangle((cols, y), 1, 1, facecolor=blended, edgecolor='black', linewidth=0.8)
        ax.add_patch(rect)
        if show_labels:
            ax.text(cols + 0.5, y + 0.5, blended, color='white' if is_dark(blended) else 'black',
                    ha='center', va='center', fontsize=7, fontweight='bold')

    plt.tight_layout()
    if save_path:
        plt.savefig(save_path, dpi=300)
    plt.show()

# --- Run as standalone script ---
if __name__ == "__main__":
    hex_codes = [
        "#DF221E", "#A52516", "#A52A2A", "#650808", "#FA775E", "#C77768",
        "#B54146", "#531320", "#FA88AA", "#FF7260", "#DF3109", "#BA3017",
        "#E20C7C", "#4D182D"
    ]

    r = 2  # Change to 3 for triplets

    combos = color_combinations(hex_codes, r)

    print(f"Generated {len(combos)} combinations of {r} colors.")
    print("Sample with mixed color:")
    for c in combos[:5]:
        print(f"{c} → Mixed: {mix_colors(c)}")

    # Visualize all combinations with their resulting blend
    visualize_hex_combinations(combos[:20], cols=r, show_labels=True)

import itertools
import matplotlib.pyplot as plt
import math

def color_combinations(hex_codes, r):
    return list(itertools.combinations(hex_codes, r))

def hex_to_rgb(hex_color):
    hex_color = hex_color.lstrip('#')
    return tuple(int(hex_color[i:i+2], 16) for i in (0, 2, 4))

def rgb_to_hex(rgb):
    return '#{:02X}{:02X}{:02X}'.format(*rgb)

def mix_colors(combo):
    rgbs = [hex_to_rgb(c) for c in combo]
    avg_rgb = tuple(sum(channel) // len(channel) for channel in zip(*rgbs))
    return rgb_to_hex(avg_rgb)

def is_dark(hex_color):
    r, g, b = hex_to_rgb(hex_color)
    luminance = 0.299 * r + 0.587 * g + 0.114 * b
    return luminance < 150

def visualize_hex_combinations(hex_combos, r, title, show_labels=True, save_path=None):
    rows = len(hex_combos)
    fig, ax = plt.subplots(figsize=((r + 1) * 2, rows * 0.6))
    ax.set_xlim(0, r + 1)
    ax.set_ylim(0, rows)
    ax.set_xticks([])
    ax.set_yticks([])
    ax.set_aspect('equal')
    fig.suptitle(title, fontsize=14)

    for row_idx, combo in enumerate(hex_combos):
        y = rows - 1 - row_idx
        for col_idx, hex_color in enumerate(combo):
            x = col_idx
            rect = plt.Rectangle((x, y), 1, 1, facecolor=hex_color, edgecolor='black', linewidth=0.3)
            ax.add_patch(rect)
            if show_labels:
                ax.text(x + 0.5, y + 0.5, hex_color, color='white' if is_dark(hex_color) else 'black',
                        ha='center', va='center', fontsize=7)

        blended = mix_colors(combo)
        rect = plt.Rectangle((r, y), 1, 1, facecolor=blended, edgecolor='black', linewidth=0.8)
        ax.add_patch(rect)
        if show_labels:
            ax.text(r + 0.5, y + 0.5, blended, color='white' if is_dark(blended) else 'black',
                    ha='center', va='center', fontsize=7, fontweight='bold')

    plt.tight_layout()
    if save_path:
        plt.savefig(save_path, dpi=300)
    plt.show()

# --- Run as standalone script ---
if __name__ == "__main__":
    hex_codes = [
        "#DF221E", "#A52516", "#A52A2A", "#650808", "#FA775E", "#C77768",
        "#B54146", "#531320", "#FA88AA", "#FF7260", "#DF3109", "#BA3017",
        "#E20C7C", "#4D182D"
    ]

    n = len(hex_codes)
    doubles = math.comb(n, 2)
    triplets = math.comb(n, 3)
    total_combos = doubles + triplets

    print(f"Total hex codes: {n}")
    print(f"Total possible combinations (doubles + triplets): {total_combos}")
    print(f"- 2-color combinations: {doubles}")
    print(f"- 3-color combinations: {triplets}")

    # ---- 2-Color Combinations ----
    r2 = 2
    combos2 = color_combinations(hex_codes, r2)
    print(f"\nFirst 5 2-color combinations with blends:")
    for c in combos2[:5]:
        print(f"{c} → Mixed: {mix_colors(c)}")
    visualize_hex_combinations(combos2[:20], r=r2, title="2-Color Combinations + Blends")

    # ---- 3-Color Combinations ----
    r3 = 3
    combos3 = color_combinations(hex_codes, r3)
    print(f"\nFirst 5 3-color combinations with blends:")
    for c in combos3[:5]:
        print(f"{c} → Mixed: {mix_colors(c)}")
    visualize_hex_combinations(combos3[:20], r=r3, title="3-Color Combinations + Blends")

import itertools
import matplotlib.pyplot as plt
import math
from matplotlib.backends.backend_pdf import PdfPages
from datetime import datetime

def color_combinations(hex_codes, r):
    return list(itertools.combinations(hex_codes, r))

def hex_to_rgb(hex_color):
    hex_color = hex_color.lstrip('#')
    return tuple(int(hex_color[i:i+2], 16) for i in (0, 2, 4))

def rgb_to_hex(rgb):
    return '#{:02X}{:02X}{:02X}'.format(*rgb)

def mix_colors(combo):
    rgbs = [hex_to_rgb(c) for c in combo]
    avg_rgb = tuple(sum(channel) // len(channel) for channel in zip(*rgbs))
    return rgb_to_hex(avg_rgb)

def is_dark(hex_color):
    r, g, b = hex_to_rgb(hex_color)
    luminance = 0.299 * r + 0.587 * g + 0.114 * b
    return luminance < 150

def create_combination_pages(hex_combos, r, title, show_labels=True, max_rows_per_page=30):
    pages = []
    for i in range(0, len(hex_combos), max_rows_per_page):
        chunk = hex_combos[i:i + max_rows_per_page]
        rows = len(chunk)
        fig, ax = plt.subplots(figsize=((r + 1) * 2, rows * 0.6))
        ax.set_xlim(0, r + 1)
        ax.set_ylim(0, rows)
        ax.set_xticks([])
        ax.set_yticks([])
        ax.set_aspect('equal')
        fig.suptitle(f"{title} (Page {i // max_rows_per_page + 1})", fontsize=14)

        for row_idx, combo in enumerate(chunk):
            y = rows - 1 - row_idx
            for col_idx, hex_color in enumerate(combo):
                x = col_idx
                rect = plt.Rectangle((x, y), 1, 1, facecolor=hex_color, edgecolor='black', linewidth=0.3)
                ax.add_patch(rect)
                if show_labels:
                    ax.text(x + 0.5, y + 0.5, hex_color, color='white' if is_dark(hex_color) else 'black',
                            ha='center', va='center', fontsize=7)

            blended = mix_colors(combo)
            rect = plt.Rectangle((r, y), 1, 1, facecolor=blended, edgecolor='black', linewidth=0.8)
            ax.add_patch(rect)
            if show_labels:
                ax.text(r + 0.5, y + 0.5, blended, color='white' if is_dark(blended) else 'black',
                        ha='center', va='center', fontsize=7, fontweight='bold')

        plt.tight_layout()
        pages.append(fig)
    return pages

def create_cover_page(n_colors, num_doubles, num_triplets, total):
    fig, ax = plt.subplots(figsize=(8.5, 11))
    ax.axis('off')

    text = f"""
    COLOR COMBINATION CATALOG
    -------------------------
    Total Hex Codes: {n_colors}
    
    Total Combinations: {total}
    - 2-Color Combinations: {num_doubles}
    - 3-Color Combinations: {num_triplets}
    
    Generated on: {datetime.now().strftime('%B %d, %Y at %I:%M %p')}
    
    Each row in this catalog shows:
    • The individual colors
    • Their blended (averaged) shade
    """

    ax.text(0.1, 0.7, text.strip(), fontsize=14, verticalalignment='top', wrap=True)
    return fig

# --- Run as standalone script ---
if __name__ == "__main__":
    hex_codes = [
        "#DF221E", "#A52516", "#A52A2A", "#650808", "#FA775E", "#C77768",
        "#B54146", "#531320", "#FA88AA", "#FF7260", "#DF3109", "#BA3017",
        "#E20C7C", "#4D182D"
    ]

    n = len(hex_codes)
    doubles = math.comb(n, 2)
    triplets = math.comb(n, 3)
    total_combos = doubles + triplets

    print(f"Total hex codes: {n}")
    print(f"Total possible combinations (doubles + triplets): {total_combos}")
    print(f"- 2-color combinations: {doubles}")
    print(f"- 3-color combinations: {triplets}")

    # Generate combinations
    combos2 = color_combinations(hex_codes, 2)
    combos3 = color_combinations(hex_codes, 3)

    # Generate pages
    cover = create_cover_page(n, doubles, triplets, total_combos)
    pages2 = create_combination_pages(combos2, 2, "2-Color Combinations + Blends")
    pages3 = create_combination_pages(combos3, 3, "3-Color Combinations + Blends")

    # Save to single PDF with metadata
    metadata = {
        'Title': 'Color Combinations Catalog',
        'Author': 'Generated via Python & Matplotlib',
        'Subject': 'Cosmetic Shade Blending Visualization',
        'Keywords': 'color, hex, blending, cosmetics, combinations, foundation, lipstick'
    }
# Inside if __name__ == "__main__":
def create_color_categories_page(hex_codes):
    from matplotlib.patches import Rectangle
    import colorsys

    def classify(hex_code):
        r, g, b = hex_to_rgb(hex_code)
        h, l, s = colorsys.rgb_to_hls(r / 255, g / 255, b / 255)

        if l < 0.15:
            return "Dark/Neutral"
        elif h < 0.05 or h > 0.95:
            return "Red"
        elif 0.05 <= h <= 0.1:
            return "Orange"
        elif 0.1 < h <= 0.14:
            return "Brown"
        elif 0.9 >= h >= 0.8:
            return "Pink"
        else:
            return "Other"

    categories = {}
    for code in hex_codes:
        cat = classify(code)
        categories.setdefault(cat, []).append(code)

    fig, ax = plt.subplots(figsize=(8.5, 11))
    ax.axis('off')
    y = 1.0

    ax.text(0.05, y, "Color Categories", fontsize=16, weight='bold')
    y -= 0.07

    for cat, codes in categories.items():
        ax.text(0.05, y, f"{cat}:", fontsize=13, weight='bold')
        y -= 0.05

        for i, code in enumerate(codes):
            x = 0.05 + (i % 6) * 0.15
            row_y = y - (i // 6) * 0.07

            rect = Rectangle((x, row_y), 0.12, 0.05, facecolor=code, edgecolor='black')
            ax.add_patch(rect)
            ax.text(x + 0.06, row_y + 0.025, code, ha='center', va='center',
                    fontsize=8, color='white' if is_dark(code) else 'black')

        y = row_y - 0.08  # space before next category

    return fig

# Inside if __name__ == "__main__":
with PdfPages("color_combinations_catalog_full.pdf", metadata=metadata) as pdf:
    # Add cover page
    pdf.savefig(cover)
    plt.close(cover)
    
    # Add color categories page
    color_category_page = create_color_categories_page(hex_codes)
    pdf.savefig(color_category_page)
    plt.close(color_category_page)
    
    # Add combination pages
    for fig in pages2 + pages3:
        pdf.savefig(fig)
        plt.close(fig)

print("\n✅ PDF saved as 'color_combinations_catalog_full.pdf' with all combinations, a cover page, and metadata.")
def create_color_categories_page(hex_codes):
    from matplotlib.patches import Rectangle
    import colorsys

    def classify(hex_code):
        r, g, b = hex_to_rgb(hex_code)
        h, l, s = colorsys.rgb_to_hls(r / 255, g / 255, b / 255)

        if l < 0.15:
            return "Dark/Neutral"
        elif h < 0.05 or h > 0.95:
            return "Red"
        elif 0.05 <= h <= 0.1:
            return "Orange"
        elif 0.1 < h <= 0.14:
            return "Brown"
        elif 0.9 >= h >= 0.8:
            return "Pink"
        else:
            return "Other"

    categories = {}
    for code in hex_codes:
        cat = classify(code)
        categories.setdefault(cat, []).append(code)

    fig, ax = plt.subplots(figsize=(8.5, 11))
    ax.axis('off')
    y = 1.0

    ax.text(0.05, y, "Color Categories", fontsize=16, weight='bold')
    y -= 0.07

    for cat, codes in categories.items():
        ax.text(0.05, y, f"{cat}:", fontsize=13, weight='bold')
        y -= 0.05

        for i, code in enumerate(codes):
            x = 0.05 + (i % 6) * 0.15
            row_y = y - (i // 6) * 0.07

            rect = Rectangle((x, row_y), 0.12, 0.05, facecolor=code, edgecolor='black')
            ax.add_patch(rect)
            ax.text(x + 0.06, row_y + 0.025, code, ha='center', va='center',
                    fontsize=8, color='white' if is_dark(code) else 'black')

        y = row_y - 0.08  # space before next category

    return fig

import streamlit as st
import itertools
import matplotlib.pyplot as plt
import io
from matplotlib.backends.backend_pdf import PdfPages
from datetime import datetime

def hex_to_rgb(hex_color):
    hex_color = hex_color.lstrip('#')
    return tuple(int(hex_color[i:i+2], 16) for i in (0, 2, 4))

def rgb_to_hex(rgb):
    return '#{:02X}{:02X}{:02X}'.format(*rgb)

def is_dark(hex_color):
    r, g, b = hex_to_rgb(hex_color)
    luminance = 0.299 * r + 0.587 * g + 0.114 * b
    return luminance < 150

def mix_colors(combo):
    rgbs = [hex_to_rgb(c) for c in combo]
    avg_rgb = tuple(sum(channel) // len(channel) for channel in zip(*rgbs))
    return rgb_to_hex(avg_rgb)

def generate_combinations(hex_codes, r):
    return list(itertools.combinations(hex_codes, r))

def generate_pdf(hex_codes, combos, r):
    buffer = io.BytesIO()
    with PdfPages(buffer) as pdf:
        fig_cover, ax = plt.subplots(figsize=(8.5, 11))
        ax.axis('off')
        ax.text(0.1, 0.85, "COLOR COMBINATION CATALOG", fontsize=20, weight='bold')
        ax.text(0.1, 0.7, f"Generated on: {datetime.now().strftime('%B %d, %Y at %I:%M %p')}", fontsize=12)
        ax.text(0.1, 0.65, f"Total Hex Codes: {len(hex_codes)}", fontsize=12)
        ax.text(0.1, 0.6, f"Total {r}-Color Combinations: {len(combos)}", fontsize=12)
        pdf.savefig(fig_cover)
        plt.close(fig_cover)

        per_page = 30
        for i in range(0, len(combos), per_page):
            subset = combos[i:i + per_page]
            rows = len(subset)
            fig, ax = plt.subplots(figsize=((r + 1) * 2, rows * 0.6))
            ax.set_xlim(0, r + 1)
            ax.set_ylim(0, rows)
            ax.set_xticks([])
            ax.set_yticks([])
            ax.set_aspect('equal')
            fig.suptitle(f"{r}-Color Combinations (Page {i // per_page + 1})", fontsize=14)

            for row_idx, combo in enumerate(subset):
                y = rows - 1 - row_idx
                for col_idx, color in enumerate(combo):
                    rect = plt.Rectangle((col_idx, y), 1, 1, facecolor=color, edgecolor='black')
                    ax.add_patch(rect)
                    ax.text(col_idx + 0.5, y + 0.5, color, ha='center', va='center',
                            fontsize=7, color='white' if is_dark(color) else 'black')
                blended = mix_colors(combo)
                rect = plt.Rectangle((r, y), 1, 1, facecolor=blended, edgecolor='black', linewidth=0.8)
                ax.add_patch(rect)
                ax.text(r + 0.5, y + 0.5, blended, ha='center', va='center',
                        fontsize=8, weight='bold', color='white' if is_dark(blended) else 'black')

            plt.tight_layout()
            pdf.savefig(fig)
            plt.close(fig)

    buffer.seek(0)
    return buffer
st.set_page_config(page_title="Color Combo PDF Generator", layout="centered")

st.title("🎨 Color Combination + Blend Generator")
st.write("Upload your hex color codes, choose how many per combination, and get a visual PDF!")

uploaded_file = st.file_uploader("Upload a .txt or .csv file with hex codes (one per line)", type=["txt", "csv"])
r = st.radio("Number of colors per combination", [2, 3])

if uploaded_file:
    hex_codes = [line.strip() for line in uploaded_file.readlines()]
    hex_codes = [c.decode("utf-8") if isinstance(c, bytes) else c for c in hex_codes]
    hex_codes = [c for c in hex_codes if c.startswith("#") and len(c) == 7]
    all_hex_codes = list(set(hex_codes + st.session_state["saved_custom_colors"]))


    st.success(f"Using {len(all_hex_codes)} total hex codes (uploaded + manual).")
    combos = generate_combinations(all_hex_codes, r)


    preview_limit = st.slider("Preview how many combinations", min_value=5, max_value=50, value=20)
    st.pyplot(render_combination_preview(combos, r, preview_count=preview_limit))

    if st.button("📄 Generate PDF Catalog"):
        with st.spinner("Rendering your combinations..."):
            pdf_bytes = generate_pdf(all_hex_codes, combos, r)
            st.success("✅ PDF generated!")
            st.download_button(
                label="📥 Download PDF",
                data=pdf_bytes,
                file_name="color_combinations.pdf",
                mime="application/pdf"
            )

            st.success("PDF generated!")

            st.download_button(
                label="📄 Download PDF",
                data=pdf_bytes,
                file_name="color_combinations.pdf",
                mime="application/pdf"
            )
from matplotlib.figure import Figure

def render_combination_preview(hex_combos, r, preview_count=20):
    rows = min(len(hex_combos), preview_count)
    fig = Figure(figsize=((r + 1) * 2, rows * 0.6))
    ax = fig.subplots()
    ax.set_xlim(0, r + 1)
    ax.set_ylim(0, rows)
    ax.set_xticks([])
    ax.set_yticks([])
    ax.set_aspect('equal')
    fig.suptitle(f"Preview of {r}-Color Combinations", fontsize=14)

    for row_idx, combo in enumerate(hex_combos[:rows]):
        y = rows - 1 - row_idx
        for col_idx, color in enumerate(combo):
            rect = plt.Rectangle((col_idx, y), 1, 1, facecolor=color, edgecolor='black')
            ax.add_patch(rect)
            ax.text(col_idx + 0.5, y + 0.5, color, ha='center', va='center',
                    fontsize=7, color='white' if is_dark(color) else 'black')

        blended = mix_colors(combo)
        rect = plt.Rectangle((r, y), 1, 1, facecolor=blended, edgecolor='black', linewidth=0.8)
        ax.add_patch(rect)
        ax.text(r + 0.5, y + 0.5, blended, ha='center', va='center',
                fontsize=8, weight='bold', color='white' if is_dark(blended) else 'black')

    return fig

# Add manual color picker
st.markdown("---")
st.subheader("🎯 Add Custom Colors Manually")

custom_colors = []
add_color = st.color_picker("Pick a color to add", "#FFFFFF")
if st.button("➕ Add Color"):
    custom_colors.append(add_color)

# Store uploaded and added colors
if "saved_custom_colors" not in st.session_state:
    st.session_state["saved_custom_colors"] = []

# Save and show added colors
if add_color and add_color not in st.session_state["saved_custom_colors"]:
    st.session_state["saved_custom_colors"].append(add_color)

if st.session_state["saved_custom_colors"]:
    st.write("🖍️ Custom Colors Added:")
    st.write(st.session_state["saved_custom_colors"])

gdrive_link = upload_to_gdrive(pdf_bytes, "color_combinations.pdf")

import app.py  # runs the script on import if it has top-level code
# OR call a function from it

with open("app.py") as f:
    code = f.read()
    exec(code)

"""
Color Combinator - Core Library

This module provides functionality for generating, visualizing, 
and exporting color combinations with their blended results.
"""

import itertools
import math
import matplotlib.pyplot as plt
import matplotlib
matplotlib.use('Agg')  # Use non-interactive backend
from matplotlib.backends.backend_pdf import PdfPages
from datetime import datetime
import os
import io
import base64

class ColorCombinator:
    def __init__(self, hex_codes=None):
        """
        Initialize with optional list of hex color codes.
        """
        self.hex_codes = hex_codes or []
        
    def set_colors(self, hex_codes):
        """
        Set the list of hex color codes.
        """
        self.hex_codes = hex_codes
        return self
    
    def get_color_stats(self):
        """
        Get statistics about the possible color combinations.
        """
        n = len(self.hex_codes)
        doubles = math.comb(n, 2) if n >= 2 else 0
        triplets = math.comb(n, 3) if n >= 3 else 0
        
        return {
            "total_colors": n,
            "pairs_count": doubles,
            "triplets_count": triplets,
            "total_combinations": doubles + triplets
        }
    
    def generate_combinations(self, r):
        """
        Generate all combinations of r colors from the hex codes.
        
        Args:
            r: Number of colors per combination (2 for pairs, 3 for triplets)
            
        Returns:
            List of color combinations
        """
        if len(self.hex_codes) < r:
            return []
            
        return list(itertools.combinations(self.hex_codes, r))
    
    @staticmethod
    def hex_to_rgb(hex_color):
        """
        Convert hex color to RGB tuple.
        """
        hex_color = hex_color.lstrip('#')
        return tuple(int(hex_color[i:i+2], 16) for i in (0, 2, 4))
    
    @staticmethod
    def rgb_to_hex(rgb):
        """
        Convert RGB tuple to hex color.
        """
        return '#{:02X}{:02X}{:02X}'.format(*rgb)
    
    @staticmethod
    def mix_colors(combo):
        """
        Average RGB values to get a blended color.
        """
        rgbs = [ColorCombinator.hex_to_rgb(c) for c in combo]
        avg_rgb = tuple(sum(channel) // len(channel) for channel in zip(*rgbs))
        return ColorCombinator.rgb_to_hex(avg_rgb)
    
    @staticmethod
    def is_dark(hex_color):
        """
        Determine if a color is dark or light using luminance.
        """
        r, g, b = ColorCombinator.hex_to_rgb(hex_color)
        luminance = 0.299 * r + 0.587 * g + 0.114 * b
        return luminance < 150
    
    def create_visualization_figure(self, hex_combos, r, title, show_labels=True, max_rows=30):
        """
        Create a matplotlib figure showing color combinations.
        
        Args:
            hex_combos: List of color combinations
            r: Number of colors per combination
            title: Title for the figure
            show_labels: Whether to show hex code labels
            max_rows: Maximum number of rows to display
            
        Returns:
            Matplotlib figure
        """
        hex_combos = hex_combos[:max_rows]  # Limit to max_rows
        rows = len(hex_combos)
        if rows == 0:
            return None
            
        fig, ax = plt.subplots(figsize=((r + 1) * 2, rows * 0.6))
        ax.set_xlim(0, r + 1)
        ax.set_ylim(0, rows)
        ax.set_xticks([])
        ax.set_yticks([])
        ax.set_aspect('equal')
        fig.suptitle(title, fontsize=14)

        for row_idx, combo in enumerate(hex_combos):
            y = rows - 1 - row_idx
            for col_idx, hex_color in enumerate(combo):
                x = col_idx
                rect = plt.Rectangle((x, y), 1, 1, facecolor=hex_color, edgecolor='black', linewidth=0.3)
                ax.add_patch(rect)
                if show_labels:
                    ax.text(x + 0.5, y + 0.5, hex_color, 
                            color='white' if self.is_dark(hex_color) else 'black',
                            ha='center', va='center', fontsize=7)

            blended = self.mix_colors(combo)
            rect = plt.Rectangle((r, y), 1, 1, facecolor=blended, edgecolor='black', linewidth=0.8)
            ax.add_patch(rect)
            if show_labels:
                ax.text(r + 0.5, y + 0.5, blended, 
                        color='white' if self.is_dark(blended) else 'black',
                        ha='center', va='center', fontsize=7, fontweight='bold')

        plt.tight_layout()
        return fig
    
    def create_cover_page(self):
        """
        Create a cover page for the PDF catalog.
        """
        stats = self.get_color_stats()
        
        fig, ax = plt.subplots(figsize=(8.5, 11))
        ax.axis('off')

        text = f"""
        COLOR COMBINATION CATALOG
        -------------------------
        Total Hex Codes: {stats['total_colors']}
        
        Total Combinations: {stats['total_combinations']}
        - 2-Color Combinations: {stats['pairs_count']}
        - 3-Color Combinations: {stats['triplets_count']}
        
        Generated on: {datetime.now().strftime('%B %d, %Y at %I:%M %p')}
        
        Each row in this catalog shows:
        • The individual colors
        • Their blended (averaged) shade
        """

        ax.text(0.1, 0.7, text.strip(), fontsize=14, verticalalignment='top', wrap=True)
        
        # Display the hex codes
        colors_text = "Colors in this catalog:\n" + "\n".join(self.hex_codes)
        ax.text(0.1, 0.3, colors_text, fontsize=10, verticalalignment='top', wrap=True)
        
        return fig
    
    def create_combination_pages(self, hex_combos, r, title, show_labels=True, max_rows_per_page=30):
        """
        Create multiple pages for the PDF catalog.
        """
        pages = []
        for i in range(0, len(hex_combos), max_rows_per_page):
            chunk = hex_combos[i:i + max_rows_per_page]
            rows = len(chunk)
            fig, ax = plt.subplots(figsize=((r + 1) * 2, rows * 0.6))
            ax.set_xlim(0, r + 1)
            ax.set_ylim(0, rows)
            ax.set_xticks([])
            ax.set_yticks([])
            ax.set_aspect('equal')
            fig.suptitle(f"{title} (Page {i // max_rows_per_page + 1})", fontsize=14)

            for row_idx, combo in enumerate(chunk):
                y = rows - 1 - row_idx
                for col_idx, hex_color in enumerate(combo):
                    x = col_idx
                    rect = plt.Rectangle((x, y), 1, 1, facecolor=hex_color, edgecolor='black', linewidth=0.3)
                    ax.add_patch(rect)
                    if show_labels:
                        ax.text(x + 0.5, y + 0.5, hex_color, 
                                color='white' if self.is_dark(hex_color) else 'black',
                                ha='center', va='center', fontsize=7)

                blended = self.mix_colors(combo)
                rect = plt.Rectangle((r, y), 1, 1, facecolor=blended, edgecolor='black', linewidth=0.8)
                ax.add_patch(rect)
                if show_labels:
                    ax.text(r + 0.5, y + 0.5, blended, 
                            color='white' if self.is_dark(blended) else 'black',
                            ha='center', va='center', fontsize=7, fontweight='bold')

            plt.tight_layout()
            pages.append(fig)
        return pages
    
    def export_pdf(self, output_path):
        """
        Export all combinations to a PDF file.
        
        Args:
            output_path: Path to save the PDF
            
        Returns:
            Path to the saved PDF file
        """
        with PdfPages(output_path) as pdf:
            # Add cover page
            cover = self.create_cover_page()
            pdf.savefig(cover)
            plt.close(cover)
            
            # Add 2-color combinations
            combos2 = self.generate_combinations(2)
            if combos2:
                pages = self.create_combination_pages(combos2, 2, "2-Color Combinations + Blends")
                for page in pages:
                    pdf.savefig(page)
                    plt.close(page)
            
            # Add 3-color combinations
            combos3 = self.generate_combinations(3)
            if combos3:
                pages = self.create_combination_pages(combos3, 3, "3-Color Combinations + Blends")
                for page in pages:
                    pdf.savefig(page)
                    plt.close(page)
                    
        return output_path
    
    def get_image_base64(self, hex_combos, r, title, show_labels=True, max_rows=30):
        """
        Generate a base64 encoded image of the visualization.
        
        Args:
            hex_combos: List of color combinations
            r: Number of colors per combination
            title: Title for the figure
            show_labels: Whether to show hex code labels
            max_rows: Maximum number of rows to display
            
        Returns:
            Base64 encoded image
        """
        fig = self.create_visualization_figure(hex_combos, r, title, show_labels, max_rows)
        if fig is None:
            return None
            
        buf = io.BytesIO()
        fig.savefig(buf, format='png', dpi=100)
        plt.close(fig)
        buf.seek(0)
        
        # Convert to base64
        img_str = base64.b64encode(buf.read()).decode('utf-8')
        return img_str
    
    """
Color Combinator Web Application

This application provides a web interface for generating, 
visualizing, and exporting color combinations.
"""

from flask import Flask, render_template, request, send_file, redirect, url_for, jsonify
import os
import tempfile
from werkzeug.utils import secure_filename
from colorcombinator import ColorCombinator
import re

app = Flask(__name__)
app.config['UPLOAD_FOLDER'] = tempfile.gettempdir()
app.config['MAX_CONTENT_LENGTH'] = 16 * 1024 * 1024  # 16MB max upload size

@app.route('/')
def index():
    """
    Render the main page with the color input form.
    """
    return render_template('index.html')

@app.route('/process', methods=['POST'])
def process():
    """
    Process the submitted colors and generate combinations.
    """
    # Get colors from form
    colors_input = request.form.get('colors', '')
    
    # Parse colors - support comma, space, or newline separated values
    colors = re.findall(r'#[0-9A-Fa-f]{6}', colors_input)
    
    # Validate colors (must have at least 2 for combinations)
    if len(colors) < 2:
        return render_template('index.html', 
                              error="Please enter at least 2 valid hex colors (format: #RRGGBB)")
    
    # Create color combinator
    combinator = ColorCombinator(colors)
    stats = combinator.get_color_stats()
    
    # Generate image previews (limit to 20 rows for browser performance)
    pairs_img = None
    triplets_img = None
    
    if stats['pairs_count'] > 0:
        combos2 = combinator.generate_combinations(2)
        pairs_img = combinator.get_image_base64(combos2[:20], 2, "2-Color Combinations + Blends")
    
    if stats['triplets_count'] > 0:
        combos3 = combinator.generate_combinations(3)
        triplets_img = combinator.get_image_base64(combos3[:20], 3, "3-Color Combinations + Blends")
    
    return render_template('results.html', 
                          colors=colors,
                          stats=stats,
                          pairs_img=pairs_img,
                          triplets_img=triplets_img)

@app.route('/export_pdf', methods=['POST'])
def export_pdf():
    """
    Generate and download a PDF of the color combinations.
    """
    # Get colors from form
    colors_input = request.form.get('colors', '')
    
    # Parse colors
    colors = re.findall(r'#[0-9A-Fa-f]{6}', colors_input)
    
    # Validate colors
    if len(colors) < 2:
        return jsonify({'error': 'Not enough valid colors provided'}), 400
    
    # Create color combinator
    combinator = ColorCombinator(colors)
    
    # Create temporary file for PDF
    fd, temp_path = tempfile.mkstemp(suffix='.pdf')
    os.close(fd)
    
    # Export to PDF
    try:
        combinator.export_pdf(temp_path)
        return send_file(temp_path, 
                        mimetype='application/pdf',
                        as_attachment=True,
                        download_name='color_combinations.pdf')
    except Exception as e:
        return jsonify({'error': str(e)}), 500

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000, debug=False)





    
