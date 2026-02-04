# AI Pricing Assistant for Small Indian Businesses - Requirements


## Goals


**Primary Goal**: Help Indian micro-sellers confidently set optimal product prices using AI-powered conversational guidance and GST-aware calculations.


**Success Metrics**:
- Users get a safe price in under 3 minutes with minimal inputs
- Prevents pricing below cost and protects target profit margins
- Users revisit pricing cards to update costs and refine strategies


## Problem Statement


Indian micro-sellers (handmade crafters, resellers, home businesses) struggle with pricing because they:
- Consistently underprice products and lose money
- Find traditional pricing tools too complex
- Need mobile-first solutions for e-commerce
- Lack pricing confidence and business knowledge


**Example**: Rani sells crochet bouquets on Instagram and keeps underpricing. In 60 seconds the assistant outputs a safe profitable price with clear reasoning and warns her about losses from underpricing.


## Why AI


**AI is Essential for Non-Technical Indian Micro-Sellers**:


Many Indian micro-sellers are teenagers, home entrepreneurs, or older sellers who find traditional business tools intimidating. AI transforms pricing from a complex business calculation into a natural conversation.


**Key AI Value**:
- **Conversation over Forms**: Teen sellers can say "I make earrings with beads" instead of filling category dropdowns
- **Progressive Disclosure**: AI asks follow-up questions only when needed, this avoids overwhelming the user
- **Guided Reasoning**: Explains "why this price" in simple terms, building pricing confidence
- **Builds Trust**: Transparent assumptions and explanations help sellers understand and trust recommendations


## Requirements


### Requirement 1: AI-Powered Product Intake & Data Connection


**User Story**: As a micro-seller, I want to describe my product naturally in Hinglish and optionally connect my existing data, so the AI can understand what I'm selling without filling complex forms or re-entering data repeatedly.


**Acceptance Criteria**:
1. System initiates conversational chat interface for product entry
2. AI extracts product name, category, and type (handmade/reselling) from natural language descriptions
3. When AI cannot understand user response, system provides 3-6 contextual options(along with "Don't know")
4. System proceeds with assumed defaults when user selects "Don't know"
5. Complete product intake achievable within 3 minutes average
6. User can optionally upload a product image during product description; AI extracts basic product details (e.g., product type/category cues, visual attributes) to assist product intake, and continues normally if image is skipped


### Requirement 2: Intelligent Cost Analysis


**User Story**: As a micro-seller unsure about costs, I want AI guidance to identify all cost components, so I can make informed pricing decisions.


**Acceptance Criteria**:
1. AI suggests relevant cost categories based on product type (materials, labor, packaging, overhead etc)
2. System provides industry-typical cost ranges when users are uncertain
3. System sets missing cost components using category-based defaults
4. Assumed values will be visible to the users and can be edited.
5. Cost breakdown displays clearly with confidence indicators (High/Medium/Low)
6.Users can skip detailed cost analysis and use default value instead


**Confidence Level Definition**:
- **High**: User provided most values directly
- **Medium**: Inferred from user input combined with category defaults
- **Low**: Mostly assumed values with minimal user input


### Requirement 3: GST-Aware Pricing Engine


**User Story**: As a micro-seller confused about GST, I want simple GST calculations, so I can price correctly for my registration status.


**Acceptance Criteria**:
1. System asks "Are you GST registered? (Yes/No)"
2. AI suggests GST category and rate (estimates), user confirms via 2-4 selectable options(Includes ‘Not sure’)
3. If GST registered: displays base price + GST amount + final customer price separately
4. If not GST registered: shows final price only (no GST charged)
5. GST analysis is optional and can be skipped


### Requirement 4: Three-Tier Price Recommendations with Anti-Underpricing Protection


**User Story**: As a micro-seller wanting pricing options, I want multiple pricing strategies with clear profit breakdowns and protection from losses, so I can choose what works for my business without losing money.


**Pricing Formula**:
- **Total Cost** = materials + labor + packaging + overhead etc
- **Minimum Safe Price** = Total Cost + safety buffer (adjustable)
- **Low Tier** = Competitive price near market band (if data available) but never below Minimum Safe Price
- **Best Tier** = Recommended price targeting a healthy margin (default margin suggested, user adjustable)
- **Premium Tier** = Higher-margin price for premium positioning


**Acceptance Criteria**:
1. Generates exactly three pricing tiers: Low (competitive), Best (recommended), Premium (high-margin)
2. Shows profit margin percentage and absolute profit amount for each tier
3. Applies psychological pricing and rounding rules (₹249, ₹299, ₹5/₹10 increments)
4. Provides explainable reasoning for each pricing recommendation
5. Displays prominent warning: "You lose ₹X per sale at ₹Y price. Minimum safe price: ₹Z" when user selects below-cost pricing
6. Allows fine-tuning with interactive price slider that enforces minimum safe price


### Requirement 5: Competitive Price Context (Optional)


**User Story**: As a micro-seller wanting competitive positioning, I want market price context, so I can position my product appropriately.


**Acceptance Criteria**:
1. Uses curated sample dataset with price statistics (min/max/mean/median) for 100+ common products across varied categories (e.g., handmade earrings, phone cases, home decor)
2. Displays distribution statistics including min/max/median prices with sample count
3. Integrates market stats as input into recommendation engine alongside cost and margin analysis
4. Provides market match confidence score (High/Medium/Low) based on category match quality
5. Falls back seamlessly to cost-based pricing when market data unavailable for product category


### Requirement 6: Saving Product Price and Details 


**User Story**: As a micro-seller managing multiple products, I want to save all my products with their current set price, so I can update it over time.
**Acceptance Criteria**:
1. Saves finalized products as cards on mobile-optimized dashboard
2. Displays key pricing information (final price, profit margin, last updated)
3. Allows editing through conversational interface, regenerates pricing recommendations instantly when costs change
4. Products saved locally or tied to login


## Future Roadmap


- Multi-language support with Indian regional languages and voice-first interfaces
- Multi-platform pricing strategies (different prices for WhatsApp, Instagram, marketplace channels)
- Multi-product import at once from a website / Amazon / Flipkart seller channel link (with authentication)
- Business software integrations (Tally, Zoho Books, Shopify, POS systems)
- Built-in accounting and profit tracking with automated expense categorization
- Services pricing support (hourly rates, project-based pricing for freelancers)



