import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class Main {
    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> {
            JFrame frame = new JFrame("Modern Java GUI");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setSize(820, 560);
            frame.setLocationRelativeTo(null);
            frame.setContentPane(new ModernPanel());
            frame.setVisible(true);
        });
    }
}

class ModernPanel extends JPanel {
    private final JTextField searchField;
    private final JButton renderBtn;
    private final JButton hudBtn;
    private final JButton cosmeticsBtn;
    private final JButton interfaceBtn;
    private final JButton performanceBtn;
    private final JButton toggleBtn;
    private final JPanel cardGrid;

    private final Color bgDark = new Color(7, 8, 18);
    private final Color bgPanel = new Color(18, 17, 29);
    private final Color panelSoft = new Color(23, 22, 36);
    private final Color borderGlow = new Color(168, 93, 255);
    private final Color accent = new Color(192, 126, 255);
    private final Color accentSoft = new Color(131, 83, 255);
    private final Color text = new Color(245, 245, 255);
    private final Color muted = new Color(165, 165, 190);
    private final Color toggleOff = new Color(64, 64, 74);
    private final Color toggleOn = new Color(186, 140, 255);

    public ModernPanel() {
        setBackground(bgDark);
        setLayout(new BorderLayout(18, 18));
        setBorder(BorderFactory.createEmptyBorder(20, 20, 20, 20));

        // Top bar
        JPanel topBar = new JPanel(new BorderLayout());
        topBar.setOpaque(false);

        JPanel left = new JPanel(new FlowLayout(FlowLayout.LEFT, 10, 8));
        left.setOpaque(false);

        JLabel logo = new JLabel("V");
        logo.setFont(new Font("SansSerif", Font.BOLD, 20));
        logo.setForeground(Color.WHITE);
        logo.setOpaque(true);
        logo.setBackground(new Color(126, 85, 255));
        logo.setBorder(BorderFactory.createEmptyBorder(8, 10, 8, 10));
        logo.setHorizontalAlignment(SwingConstants.CENTER);

        JLabel title = new JLabel("VOIDCLIENT");
        title.setFont(new Font("SansSerif", Font.BOLD, 18));
        title.setForeground(text);

        JLabel fps = new JLabel("232 FPS");
        fps.setFont(new Font("SansSerif", Font.BOLD, 12));
        fps.setForeground(muted);

        JButton arrow = new JButton("⌃");
        arrow.setFocusPainted(false);
        arrow.setContentAreaFilled(false);
        arrow.setBorder(BorderFactory.createEmptyBorder(4, 8, 4, 8));
        arrow.setForeground(muted);

        left.add(logo);
        left.add(title);
        left.add(Box.createHorizontalStrut(12));
        left.add(fps);
        left.add(arrow);

        topBar.add(left, BorderLayout.WEST);

        // Main content panel
        JPanel shell = new JPanel();
        shell.setLayout(new BorderLayout());
        shell.setBackground(bgPanel);
        shell.setBorder(BorderFactory.createCompoundBorder(
                BorderFactory.createLineBorder(borderGlow, 2, true),
                BorderFactory.createEmptyBorder(16, 16, 16, 16)
        ));

        // Header row inside shell
        JPanel panelHeader = new JPanel(new BorderLayout());
        panelHeader.setOpaque(false);

        JPanel tabs = new JPanel(new FlowLayout(FlowLayout.CENTER, 8, 0));
        tabs.setOpaque(false);

        renderBtn = createTabButton("Render", true);
        hudBtn = createTabButton("HUD", false);
        cosmeticsBtn = createTabButton("Cosmetics", false);
        interfaceBtn = createTabButton("Interface", false);
        performanceBtn = createTabButton("Performance", false);

        tabs.add(renderBtn);
        tabs.add(hudBtn);
        tabs.add(cosmeticsBtn);
        tabs.add(interfaceBtn);
        tabs.add(performanceBtn);

        searchField = new JTextField("Search");
        searchField.setPreferredSize(new Dimension(180, 34));
        searchField.setBackground(new Color(21, 20, 31));
        searchField.setForeground(muted);
        searchField.setBorder(BorderFactory.createCompoundBorder(
                BorderFactory.createLineBorder(new Color(120, 120, 145), 1, true),
                BorderFactory.createEmptyBorder(5, 12, 5, 12)
        ));
        searchField.setFont(new Font("SansSerif", Font.PLAIN, 14));

        JPanel rightHeader = new JPanel(new FlowLayout(FlowLayout.RIGHT, 10, 0));
        rightHeader.setOpaque(false);

        JButton tiny1 = createSmallIconButton("⌁");
        JButton tiny2 = createSmallIconButton("◫");
        JButton tiny3 = createSmallIconButton("◌");
        JButton tiny4 = createSmallIconButton("⊞");

        rightHeader.add(tiny1);
        rightHeader.add(tiny2);
        rightHeader.add(tiny3);
        rightHeader.add(tiny4);
        rightHeader.add(searchField);

        panelHeader.add(tabs, BorderLayout.CENTER);
        panelHeader.add(rightHeader, BorderLayout.EAST);

        JPanel contentArea = new JPanel();
        contentArea.setOpaque(false);
        contentArea.setLayout(new BorderLayout(0, 16));

        JPanel titleRow = new JPanel(new BorderLayout());
        titleRow.setOpaque(false);

        JLabel heading = new JLabel("Render");
        heading.setFont(new Font("SansSerif", Font.BOLD, 32));
        heading.setForeground(text);

        JLabel subtitle = new JLabel("See the world in a different light");
        subtitle.setFont(new Font("SansSerif", Font.PLAIN, 16));
        subtitle.setForeground(muted);

        JLabel activeText = new JLabel("• 9 of 16 active");
        activeText.setFont(new Font("SansSerif", Font.PLAIN, 15));
        activeText.setForeground(muted);

        titleRow.add(heading, BorderLayout.WEST);
        titleRow.add(activeText, BorderLayout.EAST);

        contentArea.add(titleRow, BorderLayout.NORTH);

        cardGrid = new JPanel(new GridLayout(0, 4, 16, 16));
        cardGrid.setOpaque(false);

        addModuleCard("Sky", "Eight living skies, from cosmic light...", true, "☼");
        addModuleCard("Ambience", "Glowing particles drifting through the air...", true, "✦");
        addModuleCard("Afterglow", "The fallen dissolve into drifting light...", true, "◌");
        addModuleCard("Radiance", "Glowing outlines on hands, items and...", true, "✧");

        addModuleCard("Custom Crosshair", "Your aim, in Void colors", false, "✷");
        addModuleCard("Cute World", "Sparkling eyes and rosy cheeks", false, "♥");
        addModuleCard("Astral Garrage", "Cars and riders, client-side", false, "◍");
        addModuleCard("Fullbright", "See clearly in the darkest caves", false, "◎");

        addModuleCard("Zoom", "A smooth lens, one key away", false, "⌕");
        addModuleCard("Freelook", "Look around without turning", false, "◐");
        addModuleCard("Block Outline", "A cleaner outline for the block you target", false, "▣");
        addModuleCard("Name Tags", "Clean tags for players and pets", false, "⌘");

        addModuleCard("Motion Blur", "Cinematic blur while you move", false, "◔");
        addModuleCard("Time", "Set your own time of day", false, "◒");
        addModuleCard("Weather", "Glassy rain, soft snowfall", false, "☔");
        addModuleCard("Particles", "Tune how many particles you see", false, "✹");

        contentArea.add(cardGrid, BorderLayout.CENTER);

        JPanel footer = new JPanel(new FlowLayout(FlowLayout.CENTER, 0, 16));
        footer.setOpaque(false);

        JLabel footerText = new JLabel("Click to toggle   ·   Right-click for settings   ·   Esc for the orbit");
        footerText.setForeground(new Color(155, 155, 180));
        footerText.setFont(new Font("SansSerif", Font.PLAIN, 12));
        footer.add(footerText);

        JPanel bottomDock = new JPanel(new FlowLayout(FlowLayout.CENTER, 10, 0));
        bottomDock.setOpaque(false);

        JButton dock1 = createDockButton("◌");
        JButton dock2 = createDockButton("⊕");
        JButton dock3 = createDockButton("⟡");
        JButton dock4 = createDockButton("◌");

        bottomDock.add(dock1);
        bottomDock.add(dock2);
        bottomDock.add(dock3);
        bottomDock.add(dock4);

        shell.add(panelHeader, BorderLayout.NORTH);
        shell.add(contentArea, BorderLayout.CENTER);
        shell.add(footer, BorderLayout.SOUTH);

        add(topBar, BorderLayout.NORTH);
        add(shell, BorderLayout.CENTER);
        add(bottomDock, BorderLayout.SOUTH);

        // Layout spacing
        setBorder(BorderFactory.createEmptyBorder(14, 18, 18, 18));
    }

    private JButton createTabButton(String text, boolean selected) {
        JButton btn = new JButton(text);
        btn.setFocusPainted(false);
        btn.setBorder(BorderFactory.createEmptyBorder(10, 18, 10, 18));
        btn.setFont(new Font("SansSerif", Font.BOLD, 14));
        btn.setOpaque(true);
        btn.setBackground(selected ? accent : new Color(15, 15, 23));
        btn.setForeground(selected ? Color.WHITE : muted);
        btn.setBorder(BorderFactory.createCompoundBorder(
                BorderFactory.createLineBorder(selected ? accentSoft : new Color(80, 80, 100), 1, true),
                BorderFactory.createEmptyBorder(8, 18, 8, 18)
        ));

        if (!selected) {
            btn.setBackground(new Color(20, 18, 30));
        }

        return btn;
    }

    private JButton createSmallIconButton(String symbol) {
        JButton b = new JButton(symbol);
        b.setPreferredSize(new Dimension(34, 34));
        b.setFocusPainted(false);
        b.setBackground(new Color(22, 20, 33));
        b.setForeground(muted);
        b.setBorder(BorderFactory.createLineBorder(new Color(90, 90, 100), 1, true));
        return b;
    }

    private JButton createDockButton(String symbol) {
        JButton b = new JButton(symbol);
        b.setPreferredSize(new Dimension(36, 36));
        b.setFocusPainted(false);
        b.setBackground(new Color(20, 20, 30));
        b.setForeground(muted);
        b.setBorder(BorderFactory.createLineBorder(new Color(90, 90, 100), 1, true));
        return b;
    }

    private void addModuleCard(String title, String description, boolean enabled, String icon) {
        JPanel card = new JPanel(new BorderLayout(10, 8));
        card.setOpaque(true);
        card.setBackground(new Color(24, 20, 38));
        card.setBorder(BorderFactory.createCompoundBorder(
                BorderFactory.createLineBorder(new Color(114, 87, 155), 1, true),
                BorderFactory.createEmptyBorder(12, 14, 12, 14)
        ));

        JPanel top = new JPanel(new BorderLayout());
        top.setOpaque(false);

        JPanel iconBox = new JPanel(new BorderLayout());
        iconBox.setOpaque(false);
        JLabel iconLabel = new JLabel(icon, SwingConstants.CENTER);
        iconLabel.setFont(new Font("SansSerif", Font.PLAIN, 22));
        iconLabel.setForeground(enabled ? Color.WHITE : muted);
        iconLabel.setOpaque(true);
        iconLabel.setBackground(enabled ? new Color(163, 122, 255) : new Color(28, 25, 38));
        iconLabel.setBorder(BorderFactory.createLineBorder(new Color(166, 122, 255), 1, true));
        iconLabel.setPreferredSize(new Dimension(36, 36));
        iconBox.add(iconLabel, BorderLayout.CENTER);

        JCheckBox toggle = new JCheckBox();
        toggle.setSelected(enabled);
        toggle.setOpaque(false);
        toggle.setFocusPainted(false);
        toggle.setForeground(enabled ? accent : Color.WHITE);

        // Make checkbox look like a toggle switch
        toggle.setUI(new javax.swing.plaf.basic.BasicCheckBoxUI() {
            @Override
            protected void installDefaults(AbstractButton b) {
                super.installDefaults(b);
                b.setOpaque(false);
            }
        });

        toggle.setBorder(BorderFactory.createEmptyBorder());

        // Custom switch look using JToggleButton instead
        JToggleButton switchBtn = new JToggleButton();
        switchBtn.setSelected(enabled);
        switchBtn.setOpaque(false);
        switchBtn.setFocusPainted(false);
        switchBtn.setBorder(BorderFactory.createEmptyBorder(4, 0, 4, 0));
        switchBtn.setContentAreaFilled(false);

        switchBtn.setUI(new javax.swing.plaf.basic.BasicToggleButtonUI() {
            @Override
            public void paint(Graphics g, JComponent c) {
                AbstractButton b = (AbstractButton) c;
                Graphics2D g2 = (Graphics2D) g.create();
                g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);

                int w = b.getWidth();
                int h = b.getHeight();
                int trackH = 18;
                int trackW = 34;
                int x = (w - trackW) / 2;
                int y = (h - trackH) / 2;

                g2.setColor(b.isSelected() ? new Color(188, 140, 255) : new Color(100, 100, 110));
                g2.fillRoundRect(x, y, trackW, trackH, 18, 18);

                int knobSize = 12;
                int knobX = b.isSelected() ? x + trackW - knobSize - 3 : x + 3;
                int knobY = y + (trackH - knobSize) / 2;

                g2.setColor(Color.WHITE);
                g2.fillRoundRect(knobX, knobY, knobSize, knobSize, 12, 12);

                g2.dispose();
            }
        });

        top.add(iconBox, BorderLayout.WEST);
        top.add(switchBtn, BorderLayout.EAST);

        JPanel info = new JPanel();
        info.setOpaque(false);
        info.setLayout(new BoxLayout(info, BoxLayout.Y_AXIS));

        JLabel titleLabel = new JLabel(title);
        titleLabel.setFont(new Font("SansSerif", Font.BOLD, 18));
        titleLabel.setForeground(text);

        JLabel descLabel = new JLabel("<html><body style='width: 180px'>" + description + "</body></html>");
        descLabel.setFont(new Font("SansSerif", Font.PLAIN, 12));
        descLabel.setForeground(muted);

        info.add(titleLabel);
        info.add(Box.createVerticalStrut(4));
        info.add(descLabel);

        card.add(top, BorderLayout.NORTH);
        card.add(info, BorderLayout.CENTER);

        cardGrid.add(card);
    }
}
